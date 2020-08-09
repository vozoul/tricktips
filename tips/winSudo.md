# Trick & tips - Commande `sudo` sous windows

**Retranscris par Vincent le 09/08/2020**

**Scources: https://parlonsgeek.com/sudo-sous-windows/**

Vous cherchez une methode pour être administrateur de vos ligne de commande sous windows ...

Sous windows la commande de base:

`runas <OPTIONS> /useur:<USER> Program`

- exemple, ouvrir l'invite commande `cmd` depuis une commande

    `runas /noprofile /user:administrator cmd`

Un peu long ! N'est-ce pas ? Surtout si l'on ajoute des options 

pour faire fonctionnner la command `sudo` sous les differentes invite de commande utilisées sous windows, quelques etape et finish !!


- Ouvrez PowerShell (en tant qu'administrateur, ca peut éviter des conflis ou erreurs divers)
- écrivez les commandes suivantes:

    ```cmd
        // ajout du gestionnaire de paquet correspondant
        iex(new-object net.webclient).downloadstring('https://get.scoop.sh')

        // Modifiez les restrictions d'execution
        set-executionpolicy unrestricted -s cu -f

        // Installez la commande au systeme depuis le gestionnaire de paquet
        scoop install sudo
    ```

Voila c'est fini !

Dès l'ors vous pouvez lancer vos command en temps qu'administrateur ainsi:

`sudo <COMMANDE>`

example l'invite de commande `cmd`:

`sudo cmd`

plus court, non ?

Amusez-vous bien !