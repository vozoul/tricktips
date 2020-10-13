# Trick & tips - Déployer vos repos GIT

[< Sommaire](Tips)

[< Tips](Tips)

## Préambule

Vous vous êtes déjà, surement demander, comment ... ? 
- deployer rapidement un site ou une appli
- sur mon environement distant.
- sans utiliser gitlab ou github.com

## Prérequis
- En locale:
    - git
    - votre projet

- En distant:
    - un serveur fonctionnel
    - git

**Finalement ce ne sont que quelques étapes simples, (quant on le sait oui!)**


Vous avez peut-être déjà commencer le travail ? c'est pas mal !

### Coté locale

En reprenant depuis le début ...

Vous devriez avoir en locale quelque chose comme ceci:

```bash
# Machine locale (dossier de travail)

__ Mon_dossier
 |
 |__ Mon_premier_fichier.ext
 |
 |__ Un_second_fichier.ext
 |
 |__ Etc_fichiers.exts
```
**(les fichiers `*.ext`/`*.exts`, signifient `extention.s` ils peuvent être en `html`, `php`, `js`, etc... Ici ce ne sera qu'un example)**

A ce moment pour intialiser le versioning de votre projet depuis le dossier `Mon_dossier` (nom du dossier de projet)

Références dans la console:
```bash
    # Windows
    Z:\Chemin_de_mon_dossier\Mon_dossier\>

    # Linux / Macos
    <user>@<host> ~/chemin_du_dossier/Mon_dossier> $
```
**( `"Z"` est une lettre de disque dur arbitraire )**

Utilisez les commandes suivantes:

```bash
~/Mon_dossier
> $
    # initialisation de la versionnalisation du projet
    git init

    # ajouts des fichiers a inclure dans le suivi de fichier (staging)
    git add <le fchier a envoyer>

    # facultatif pour envoyer tous les fichiers ce sera representé par un point
    git add .

    # seller l'envoie de fichier
    git commit -m " `un message representatif de ce que vous envoyez` "
```
**Pour la partie locale c'est pas mal !**


### Coté distant

le serveur distant ne contient pour l'instant qu'un dossier vide 

**(attention example basé sur une infrastructure linux)**

```bash
# Serveur Distant (de déploiement)

__ /                # racine du serveur
 |__ var/
 | |__ ...
 |   |__ www/         # racine du votre site
 |     |__ ...
 |     |__ html/      # dossier accessible depuis l'exterieur
 |       |__ .
 |       |__ ..
 |
 |__ etc...
```
**(Dans une configuration classique linux)**


ça arrive ... pas d'inquiètude ...