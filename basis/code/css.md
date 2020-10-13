# TRICKS & TIPS - Css

### \- **[Acceuil](Practice)** \- **[Les bases](Basis)** \-

**Rédigé par Vandekerckhove Vincent**

**Première édition : 28/07/2020**

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
    <div ... style="color: #FF0000;" ... > contenu </div>
  ```

- Interne

  appel a un script dans l'en-tête du document

  ```code
  <head>
    <script type="text/css">... #rouge { color: #FF0000; }</script>`
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
      color: #00FF00;
    }
  </script>
</head>
<body>
  <div id="vert">
    contenu vert
  </div>
  <div style="color:#FF0000;">
    contenu rouge
  </div>
  <div class="text_bleu">
    contenu bleu
  </div>
</body>
```
```CSS
/* fichier.css */
// utilise la classe de notre éléments ici : text_bleu
.text_bleu {
  color: #0000FF;
}
```

***
exemple: (non fonctionnel sur github)

<div style="color:#00FF00;">
  contenu vert
</div>
<div  style="color:#FF0000;">
  contenu rouge
</div>
<div  style="color:#0000FF;">
  contenu bleu
</div>

***

**l'appel aux ressource externalisées est à privilégié, pour permettre d'alléger le fichier de structure de celui de présentation, afin d'assigner une tâche défini à chaque format, de façon à facilité la maintenabilité des construction et l'évolutivité du dévellopements.**