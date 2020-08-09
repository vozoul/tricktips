# Trick & tips - Commande `sudo` sous windows

**Retranscris par Vincent le 09/08/2020**

**Scources: https://parlonsgeek.com/sudo-sous-windows/**

Vous voulez ?
- Une methode pour être Super utilisateur de vos ligne de commande sous windows ?

- Retrouver le fonctionnement linux sous windows ?

pour cela sous windows la commande de base:

`runas <OPTIONS> /user:<USER> Program`

- exemple, ouvrir l'invite commande `cmd` depuis une commande

    `runas /noprofile /user:administrator cmd`

Un peu long ! N'est-ce pas ?

Surtout si l'on ajoute des options ...

Pour faire fonctionnner la command `sudo` sous les differentes invite de commande utilisées sous windows, quelques etape et finish !!

***

#### Ouvrez PowerShell **
** **(en tant qu'administrateur, ca peut éviter des conflis ou erreurs divers)**

#### Ecrivez les commandes suivantes:

- ##### Ajout du gestionnaire de paquet
    ```code
        iex(new-object net.webclient).downloadstring('https://get.scoop.sh')
    ```
    
- ##### Modifiez les restrictions d'execution
    ```code
        set-executionpolicy unrestricted -s cu -f
    ```

- ##### Installez la commande au systeme depuis le gestionnaire de paquet

    ```code
        scoop install sudo
    ```

Voila c'est fini !

***

Dès l'ors vous pouvez lancer vos command en temps qu'administrateur ainsi:

`sudo <COMMANDE>`

example l'invite de commande `cmd`:

`sudo cmd`

Plus court, non ?

Merci de votre lecture, amusez-vous bien !