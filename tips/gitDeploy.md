# Trick & tips - Déployer vos repos GIT

[< Sommaire](/README.md)

[< Tips](./README.md)

## Préambule

Vous vous êtes déjà, surement demander, comment ... ? 
- deployer rapidement un site ou une appli
- sur mon environement distant.
- sans utiliser gitlab ou github.com

**Finalement ce ne sont que quelques étapes simples, (quant on le sait oui!)**


Vous peux être déjà commencer le travail ? c'est pas mal !

En reprenant depuis le début ...

Vous devriez avoir en local quelque chose comme ceci:

```bash
# Machine locale (de travail)

__ Mon_dossier
 |__ Mon_premier_fichier.ext
 |__ Un_second_fichier.ext
 |__ Etc_fichiers.exts
```
**(les fichiers `*.ext`/`*.exts`, signifient `extention.s` ils peuvent être en `html`, `php`, `js`, etc... Ici ce ne sera qu'un example)**

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


