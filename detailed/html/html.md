# Trick & tips - HTML

**Rédigé par Vandekerckhove vincent**

**HYPERTEXT MARCKUP LANGUAGE**

Le HTML n'est pas un language de programmation, c'est un langage de structure.

il ce compose d'**éléments** entourant ou enveloppant divers partie du contenu afin de leurs donner un comportement choisi pour le document.

par exemple:


nous souhaitons ecrire un paragraphe :

- `Je m'appel vincent`

(j'aurais bien écrit "mon chat s'appel léon" mais j'ai pas de chat)

en html:

```html
<p>Je m'appel vincent</p>
```

en détail:

`<p>` = la balise ouvrante (`p` definit que c'est un paragraphe)
`Je m'appel vincent` = le contenu a faire apparaitre dans notre document sous forme de paraphe
`</p>` = balise fermante determine la fin de notre **élément paragraphe**