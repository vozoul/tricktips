# TRICKS & TIPS - Html

### \- **[Acceuil](Practice)** \- **[Les bases](Basis)** \-

**Rédigé par Vandekerckhove Vincent**

**Première édition : 28/07/2020**

## HTML (HyperText Markup Language)

**HTML language de contruction balisé**

Le language balisé va simplement definir chaque éléments de notre documents par une syntaxe simple qui sera d'ouvrir un élément insérer son contenu et/ou ses paramètres puis le refermé, d'ou parler de balisage

- **notre élément c'est : `<là>` et il s'arrête `</là>` !!**

  l'élément est donc balisé entre :

  - `<là>`
  - `</là>`

`là`, le nom utiliser au début et à la fin, doit être identique afin que le navigateur interprète correctement l'élément en question.

- **notre élément c'est : `<çà avec plein de trucs rigolos dedans />` !!**

  l'élément est donc limité (balisé) à:

  - `<çà avec plein de trucs rigolos dedans />`

## La construction d'une page

### une page commence toujours par les éléments suivants en en-tête

```html 5
<!DOCTYPE html>
<html lang="{langue utilisées}">
  <head>
    <meta ... />
    <link ... />
    <script>
      ...;
    </script>
    <style>
      ...;
    </style>
  </head>
  <body>
    ...{contenu de la page}...
```

Et ce termine ainsi

```html 5
  </body>
</html>
```

### Vous pouvez voir dans l'example précédents deux `types` de balises

- #### la balise :

  ```html 5
  <balise attr="..."> {contenu} </balise>
  ```

|              | la balise                      |                                                                                     |
| :----------- | :----------------------------- | :---------------------------------------------------------------------------------- |
| `<élément>`  | ouverture d'une balise         | creation d'un élément html                                                          |
| `attr="..."` | les attributs de notre élément | des options (on parlera de `propriétés` ou `attributs`) qui s'appliques à l'élément avec la syntaxe suivante : `{nom_attribut}="{valeur_attribut}"` **ils se situent toujours `dans` la partie ouvrante de la balise** |
| `{contenu}`  | Le contenu de la balise        | le contenu peut-être d'autres balises imbriqués, du texte, etc...                   |
| `</élément>` | fermeture d'une balise         | l'éléments s'arrête ici                                                             |

- #### la balise auto-fermente :

  ```html 5
  <balise attr="..." />
  ```

|                  | la balise auto-fermente        |                                                     |
| :--------------- | :----------------------------- | :-------------------------------------------------- |
| `<élément ...`   | ouverture d'une balise         | creation d'un élément html                          |
| `attr="..."`     | les attributs de notre élément | des options (on parlera de `propriétés` ou `attributs`) qui s'appliques à l'élément avec la syntaxe suivante : `{nom_attribut}="{valeur_attribut}"`  |
| `" />"` ou `">"` | fermeture d'une balise         | l'éléments s'arrête ici (la notation "` />`" commence à être déprécier avec le html 5 (ex: `</br>` devient `<br>`) )                            |

#### Les premières balises utilisés:

| nom                   | type                 | description                                                                                                                                       |
| :-------------------- | :------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| `!DOCTYPE {language}` | balise unique        | cette balise est unique, elle définie au navigateur le type de document qu'il va devoir interpréter                                               |
| `html`                | balise               | corps du document consultable sur un navigateur                                                                                                   |
| `head`                | balise               | en-tête du document, permet de fournir au navigateur différentes informations afin qu'il puisse interpréter le document pour le rendre à l'écran  |
| `meta`                | balise autofermente  | balises paramètres, pour le référencements et l'interprétation des éléments qui seront présents dans le document                                  |
| `link`                | balise auto-fermente | définit la relation entre le document en cours avec une ou plusieurs ressource.s externe.s                                                        |
| `script`              | balise               | donne la possibilité d'utilisé un autre type de language, et signifie au navigateur comment l'interpréter grace au attributs (paramètres ajoutés) |
| `body`                | balise               | corps du document visible par l'utilisateur                                                                                                       |

A partir de la nous avons créer un document vierge.

---

**YOUHOU ! Ma première page !**

---

**Nota : Afin d'avoir une liste plus exostives d'éléments HTML voir : [Références HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Reference) - MDN web docs**

#### Les premiers morceaux de page :

je suis une :
exemple: (non fonctionnel sur github)
***

<div>
  contenu div
  <fieldset>
    <legend>contenu legend</legend>
    contenu fieldset
  </fieldset>
  div termine ici
</div>

***

la syntaxe des éléments:

```html 5
<div>
  un contenu ici
  <fieldset>
    <legend>Le titre du bloc fieldset</legend>
    contenu du fieldset
  </fieldset>
  un autre contenu au choix ...
</div>
```
et bien d'autres

en HTML vous avez plusieurs type d'éléments des éléments de type `bloc` et d'autre de type `inline`

il ont deux comportement distinct.

Le `bloc`, va être particulièrement utile pour des conteneur afin de séparé des zones,

Le `inline`, comme son nom l'indique pour ce mettre à la suite ou integrer a une ligne, comme un lien une citation ou autre ...

n'hésitez soutout pas a vous renseigner sur les [Références HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Reference).

au delà de l'architecture structurel d'un documents html on peux y ajoutez une couche pour lui donner une forme, une couleur et ce a chaques éléments, ensemble ou partie d'un document grace au :

