# Trick & tips - Git

### \- **[Acceuil](/README.md)** \- **[Les bases](../README.md)** \-

**Rédiger par Vandekerckhove Vincent**

`GIT` est un outils de "versioning" pour vos projets de travail

Cet outil de versionning sert a prendre, en quelque sort, une "photo" de nos fichiers comme ils étaient a un instant donné. On appel ceci `l'état` des données.

Je vais pour tenter de vous aider a comprendre, faire une analogie avec un bureau de poste et des choses a envoyer vers une entreprise

### L'outil `GIT` fonctionne en plusieurs étapes:

- work-zone

      la work-zone est votre espace de travail le dossier dans lequel vous faites évoluer vos fichiers

- staged-zone

      la staged-zone est un emplacement temporaire qui vous permettra de controler ce que vous envoyez en ligne ou sur le repos distant

- repo distant

      Le repo (repository) distant, c'est le dossier cible dans lequel les fichiers modifié vont etre envoyer, pour que toute votre equipe puisse avoir les même fichiers pour un projet commun, permet de mettre a jour votre site internet pour la dernier version, etc...


### Pour versionner notre projet on peux utiliser l'image suivante:

notre projet a une version:
- MAITRE (master / Production) disons que ce sera simplement notre état fonctionnel et débugger (pour un site, ce sera la version en ligne du produit accessible par tous le monde).

- BRANCHE 1 (test) pour faire controler notre projet par d'autres (notre equipe / intervenants exterieurs), cette branche est parfois, pas mise en place sur les projets suivant l'entreprise ou le developpeur (personnelement je la trouve tres utile)

- BRANCHE +N (dev, ...) pour nous permettre de coder / debugger en tant que developpeur nos features (fonctionnalités), en gros c'est la ou on a le droit de faire des erreurs (pas trop quand même)


```code

__ Maitre ___________________________________________________
      \                                             /
       \____ Branche 1 ____________________________/_________
        \                         /
         \_____ Branche +n ______/

```


***
## Installez l'outil, on ce retrouve après ...
### **Tip** - Conseil aux utilisateurs windows

Choisissez, lorsque ça vous est proposer, d'installer les commandes bash unix, cela vous aidera beaucoup sur vos projets avenir ...
***

### Mettons ca en place

**L'outil est maintenant correctement installer avec toutes les options nécessaires**

l'utilisation de git ce fait principalement en ligne de commande, il existe des interfaces graphiques pour faire le travail, cependant sachons d'abort comment cela fonctionne.

#### état de chose au départ

Nous avons:
- un dossier `Mon_dossier`,
- un fichier `Un_fichier.txt` dedans

```bash
__ Mon_dossier/
 |__ Un_fichier.txt
```

Dans votre console:
```bash
# réfs
# windows
Z:\Chemin\Mon_dossier\>

# linux / macOs
~/Chemin/Mon_dossier/
> $
```
On va, dans un premier temps, initialiser `git` 

```bash
git init
```
***
## C'est fait !
***

## Paramètrez git pour qu'il vous reconnaisse

Cela aidera par la suite à ne pas avoir a vous identifier tout le temps

`git config`

pour faire ça :
```bash
> git config user.name "<votrenom>"             # Pensez bien aux double-guillements
> git config user.mail <votre@mail.ext>
```




Vous devriez voir maintenant un dossier protégé "`.git`"
```bash
__ Mon_dossier/
 |__ .git/
 |__ Un_fichier.txt
```
Regardons ce qui c'est passer avec la commande "`git status`" ...

```bash
> git status

On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        un_fichier.txt

nothing added to commit but untracked files present (use "git add" to track)
```

**On branch master**

le projet est sur la 'branche' principale : `master`

**No commit yet**

nous n'avons pas encore envoyer de coli

**Untracked files**

Ce sont, à ce niveau, les fichiers qui n'ont pas été ajoutés dans la `staged-zone`, ce qui veux dire qu'il ne feront pas partis des documents qui seront envoyer sur notre repo distant.

***
### **Tip** - toutes les démarches a effectuer sont annoncées a chaque action, pensez a bien lire le retour (surtout en cas d'erreur ou de `conflit`)
***

Ajouter un fichier a `staged-zone`, c'est comme préparer un paquet et mettre des choses au fur et a mesure

comme il est ecrit plus haut la command est la suivante "`git add <fichier>`"

```bash
> git add un_fichier.txt
```

***
### **Tip - staging multiple**
Si vous aviez:
```bash
  (use "git add <file>..." to include in what will be committed)
        +n_fichers.txt
        deux_fichier.txt
        un_fichier.txt
```
En admettant que vous vouliez tout envoyer

Vous pourriez utiliser la commande "`git add .`" (Attention - Il y'a un (POINT), il signifie a `git` "tout")
***

Rien, pas de réaction ?? c'est normal il n'ya pas eu d'erreur, voyons ce que nous avons ... "`git status`"

```bash
> git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   un_fichier.txt
```

- Changes to be committed:

      les changement près a être envoyer

- (use "git rm --cached <file>..." to unstage)

      commande pour `unstage`, si un fichier ne doit pas être envoyer dans le prochain paquet de données on peux utiliser cette commande

le status du fichier est `new file` ce qui est le cas `Un_fichier.txt` n'a jamais été enregistrer dans le versioning

il y a différent status: `new`, `deleted`, `modified`

comme à l'image d'un colis que l'on prépare on viens de préparer un `paquet` de données on va maintenant l'oblitérer (les marquer pour l'envoie)

autrement dis, on peut faire l'inventaire de ce qu'il y'a dans notre colis

le marquage ce fait par l'association d'un message au `paquet` de fichiers que l'on envoie.

pour faire cela on utilisera la commande `git commit -m "<notre message>"`

`-m` veux dire j'écrit mon message juste après

```bash
git commit -m "mon premier commit"
[master (root-commit) 12e3d09] mon premier commit
 1 file changed, 1 insertion(+)
 create mode 100644 un_fichier.txt
```

voila on a posé le timbre sur notre coli

une première version de notre `paquet` est prête

voyons ce qui ce passe ?
```bash
> git status
On branch master
nothing to commit, working tree clean
```
plus rien tout va bien pas d'inquietude les fichiers sont la et notre branch est propre cela nous signal simplement que le fichier present dans le projet est identique a celui du dernier paquet, d'ailleur il est passer ou le paquet faisons l'inventaire

avec la commande "`git log`"

```bash
> git log
commit 12e3d092872d21739717bac1c84bfd8dfc50928a (HEAD -> master)
Author: username <user@mail.ext>
Date:   Tue Aug 11 09:52:57 2020 +0200

    mon premier commit
```

commit `<sha>` (HEAD -> master):
- le `<sha>` est le numero du `paquet`, comme pour un colis suivi
- le `HEAD` est une référence a la branche courante, ici `master` référence utilisée par `git` pour s'y retrouver.

on reviendra sur les branches un peu plus tard

author: nom_d_utilisateur \<email_utilisateur> : la personne aillant préparer le paquet, et par extention aillant travailler sur les fichiers

la date puis le message associer

**Veillez à ce que le message soit claire, qu'il précise bien ce vous avez effectuer comme action.**

**example: "modification du fichier \<un_tel>" / "TEC - ajout de la ressource R du projet P"**

**TEC = Travail En Cours, en anglais WIP = Work In Progress, cela permet de préciser que la ressource n'est pas encore terminée (très utile pour le travail en groupe)**

***
### **Tip** - Vous avez la prossibilité de voir les logs en ecriture simplifiée et raccourcie avec `git log --oneline`
```bash
> git log --oneline
12e3d09 (HEAD -> master) mon premier commit
```
qui ce lit : \<short sha> (HEAD -> \<branch>) \<message>
***
### **Tip** - Vous pouvez ensuite voir le log en détail avec `git log <short_sha>`

```bash
> git log 12e3d09
commit 12e3d092872d21739717bac1c84bfd8dfc50928a (HEAD -> master)
Author: vozoul <vozoul@gmail.com>
Date:   Tue Aug 11 09:52:57 2020 +0200

    mon premier commit
```
***

à partir d'ici on est près pour envoyer notre `paquet`

pour envoyer un paquet il vous faut un `Repo` (Repository) distant

soit:
- paramètrer dans votre serveur distant, 
- vous utiliser des outils en ligne tel que github.com (gratuit), ou d'autre ...

il existe des solutions payantes suivant vos nécessités, besoin d'être auto-héberger, en ligne, avec des outils complémentaire tel que la gestion de projet etc

**Une section trick & tips est en préparation pour github.com afin de vous familiarisé avec l'outil**

à partir de maintenant on va devoir parmètrer notre `git` afin qu'il communique avec le serveur distant, en gros donner l'adresse au bureau de poste

```bash
> git remote add origin master https://domain.name/path_to_project.git
```

`git remote`: on annonce a git que l'on va agir sur les donnée d'envoye

`add`: on ajoute au carnet d'adresse

`origin`: nom de base pour git pour l'adresse, vous pouvez en préciser plusieurs pensez à bien les nommer

      "L'entreprise "Cod'Plus"

`master`: la branche sur laquelle envoyer les fichiers

      "le service RH"

`https://domain.name/path_to_project.git`: l'adresse du dépôt (`repo`)

      "1000, bat A, Esc B, le petit port 99999 la_ville_du_bord_de_mer LePaysImaginaire"


Voila notre etiquette finale

```bash
origin                                          # name
master                                          # branch
https://domain.name/path_to_project.git         # address
```

pour Cod'Plus

```bash
Cod'Plus                                        # Nom de l'entreprise
Service Ressources Humaine                      # Service associé
1000 le petit port                              # {
Bat A, Esc B                                    #     Adresse
99999 la_ville_du_bord_de_mer                   #
LePaysImaginaire                                # }
```

## L'envoie des données

Donc enfin un colis, une adresse il ne reste plus qu'as posé tout ça au bureau de poste et c'est parti !

```bash
# pour la première fois
> git push -u origin master

# les suivantes le -u aura fait son office
> git push
```

`git push`: on explique a `git` que l'on envoie (la toute première fois `git` ne sais ni à qui ? ni où?)

`-u`: on crée se que l'on appel un up-stream on ecrit dans le carnet d'adresse que c'est l'adresse principale et que l'on synchronise tous nos envoie avec celle-ci *

      * Pour simplifié on viens de signaler que c'est le siège social et que pour toute modification de sont infrastructure on demandera ici

`origin`: on pose l'adresse

`master`: la branche

une fois ceci fait le dossier de travail connais toute les information pour refaire l'opération de manière automatisée

      * Vous venez d'expliquer à votre secrétaire, qui et où est l'entreprise Cod'Plus. Elle envera donc les prochains colis au bon endroits sans avoir a lui répéter.

Vous connaissez maintenant les rudiments de `git` pour l'envoie de fichiers et les paramètres d'envoie

Bien sûr, pour plus de détails dans les suptilités la gestion des erreurs et des conflits, regardez la documentation sur le site de [GIT](git-scm.com)