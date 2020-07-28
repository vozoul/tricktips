# TRICKS & TIPS - Html / Css
**Par Vandekerckhove Vincent**

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
  <body></body>
</html>
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
| `attr="..."` | les attributs de notre élément | des options (on parlera de `propriétés` ou `attributs`) qui s'appliques à l'élément avec la syntaxe suivante : `{nom_attribut}="{valeur_attribut}"` |
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

## CSS (Cascading style cheat)

**Language permettant la mise en forme d'un document HTML ou XML**

le but du CSS est de séparer la structure du document et sa présentation

les documents CSS n'ont pas d'en-tête obligatoire en revanche une structure définie comme suit:

```code
SELECTEUR : {
  PROPRIETE: "VALEUR";
}
```

**rappelant vaguement le format de document [JSON](https://www.json.org/json-fr.html)**

**attention en fin de chaque couple `propriétés`: `valeur`, un `SEMICOLON` / `;` (Point-virgule) est nécessaire abolument, doivent être séparer de `deux points` / `:`**

### Les selecteurs (selecor en anglais) :

les trois __principaux__ sont  l'élément, l'id, la classe, l'attribut

dans les code HTML l'élément est la balise cible

dans l'exemple suivant les selecteurs seront:
- la balise : `div`
- l'id : `THE_ID`
- la classe : `THE_CLASS`
- l'attribut : `[type="text"]`

Vous pourrez trouver une liste plus exhaustive sur [W3SCHOOL](https://www.w3schools.com/cssref/css_selectors.asp)

exemple:

HTML
```HTML
<div id="THE_ID" class="THE_CLASS">{content}</div>
<input type="text" value="entrée de type text" />
```

LE script CSS, s'écrira de la manière suivante :

```CSS
/* choix par élément (aucun préfixes) */
div {
  propriété: valeur;
}

/* choix par id (le préfixe `#` définit que l'on utilise l'id) */
#THE_ID {
  propriété: valeur;
}


/* choix par id (le préfixe `.` définit que l'on utilise l'id) */
.THE_CLASS {
  propriété: valeur;
}

/* choix par l'attribut (on vise l'élément en affinant par l'attribut entre `[]`) */
input[type="text"] {
  propriété: valeur;
}

```

Vous comprendrez donc au travers de ces example que l'on utilisera les noms d'élément, valeur d'id/class utilisés

**Nota I: dans un document HTML, les balises et classes peuvent apparaitres à plusieurs reprise sur un même document en revanche l'id dois absolument être unique**

**Nota II: l'attribut, inhérant à l'élément, peut donc apparaitre aussi plusieurs fois au sein d'un document**

par exemple:

```html 5
<div id="1" class="une">text 1</div>
<div id="2" class="une">texte 1'</div>
<div id="3" class="six">text 2</div>
<div id="4" class="trois">texte 2'</div>
<div id="5" class="trois">text 3</div>
<div id="6" class="trois">texte 3'</div>
```
les balises sont utilisés a plusieurs reprises ainsi que les classes cependant chaque élément a un identifiant unique

**Nota III: utilisez des identifiants ou classes avec des nom représentatifs**

exemple :

```html 5
<div id="article_996" class="article">
  <h3 class="title">titre de l'article 996</h3>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. In scelerisque odio nec nunc tempor maximus. Nulla convallis faucibus eros eu molestie. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  </p>
</div>
<div id="article_997" class="article">
  <h3 class="title">titre de l'article 997</h3>
  <p>
    Lorem ipsum dolor sit amet.
  </p>
</div>
<div id="article_998" class="article">
  <h3 class="title special">titre de l'article 998</h3>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  </p>
</div>
```

vous aurez vu dans l'example précédent ceci : `class="title special"`

cet exemple signifie que les classes sont multiple:
- title
- special

l'espace qui les sépares signale que se sont deux classes distinctes

et dans le CSS on pourra donc interagir et sur le `title` comme pour tout les `title` en complétant de manière différente avec `special`

```CSS
.title {
  propriété: valeur;
}

.special {
  propriété: valeur;
}

```
pour le CSS plusieur méthodes d'appel sont utilisés

- en ligne

  dans les attribut de l'élément

  ```code
    <div ... style="background-color: #FF0000;" ... > contenu </div>
  ```

- Interne

  appel a un script dans l'en-tête du document

  ```code
  <head>
    <script type="text/css">... #rouge { background-color: #FF0000; }</script>`
    ...
  ```

- Externe

  appel a une ressource exterieur dans l'en-tête du document `fichier.css`

  ```code
  <head>
    <link href="fichier.css" rel="stylesheet">
    ...
  ```

```HTML
<!-- fichier.html -->
<head>
  <link href="fichier.css" rel="stylesheet">
  <script type="text/css">
    // utilise l'attribut id de l'élément ici : rouge
    #vert {
      background-color: #00FF00;
    }
  </script>
</head>
<body>
  <div id="vert">
    vert
  </div>
  <div style="background-color:#FF0000;">
    rouge
  </div>
  <div class="text_gray">
    gris
  </div>
</body>
```
```CSS
/* fichier.css */
// utilise la classe de notre éléments ici : text_rouge
.text_gray {
  background-color: #6f6f6f;
}
```

***
exemple:

tous les exemple donne exactement ceci:

![#00FF00](https://via.placeholder.com/100x30/00ff00/ffffff?text=vert)
![#FF0000](https://via.placeholder.com/100x30/ff0000/000000?text=rouge)
![#6F6F6F](https://via.placeholder.com/100x30/6f6f6f/ffffff?text=gris)

***

**l'appel à la structure extérieure deviens de plus en plus privilégié, pour permettre d'alléger le fichier de structure de celui de présentation, afin d'assigner une tâche défini à chaque format, de façon à facilité la maintenabilité des construction et dévellopements.**