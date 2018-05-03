<!-- # = h1 -->

# Documentation

<!-- ## = h2 -->

## Convention BEM

* B --> Block
* E --> Element
* M --> Modifier

```html
<!-- mainList = Block -->
<ul class="mainList mainList--xmas">
  <!-- mainList_item = Element -->
  <li class="mainList__item">
    <!-- mainList_itemLink = Modifier -->
    <a class="mainList__itemLink mainList__itemLink--isActive" href="/home">Home</a>
  </li>

  <!-- mainList_item = Element -->
  <li class="mainList__item">
    <!-- mainList_itemLink = Modifier -->
    <a class="mainList__itemLink" href="/about">About</a>
  </li>

  <!-- mainList_item = Element -->
  <li class="mainList__item">
    <!-- mainList_itemLink = Modifier -->
    <a class="mainList__itemLink" href="/works">Works</a>
  </li>
</ul>
```

<!-- ``` = alt GR + 7 -->

```css
.mainList {
  display: flex;
  justify-content: space-between;
  &--xmas {
    background: green;
  }
  &__item {
    list-style: none;
  }
  &__itemLink {
    color: red;
    &--isActive {
      color: white;
    }
  }
}
```

## Pseudo attributs

Les pseudo attributs `before` et `after`permettent de créer des noeuds HTML et CSS.
Ils sont essentiellement utilisées pour ajouter des ornements, des décorations ... On
peut bien entendu faire des animations avec, les positionnelener par rapport à leur
parent (relative/absolute). **Ils doivent obligatoirement avoir un `content: ''`** afin de s'afficher.

```html
<section class="cover">
  <h1 class="cover__mainTitle">Présentation des pseudo-attributs</h1>
</section>
```

```css
.cover {
  background: #fdfdfd;
  padding: 20px;
  &__mainTitle {
    text-align: center;
    font-size: 24px;
    color: green;
    position: relative;
    &::before,
    &::after {
      position: absolute;
      content: 'Yo';
      color: #fff;
      display: block;
      width: 50px;
      height: 50px;
      background: green;
      top: 0;
    }
    &::before {
      left: 0;
    }
    &::after {
      right: 0;
    }
  }
}
```

## REM, EM, % vW Sizing

### %

### EM

* Relative à la taille de son parent direct.

```css
.cover {
  font-size: 100%; /* 100% = 16px*/
  &__mainTitle {
    /* 1em = 16px / 0.8em =/= 16px */
    font-size: 0.8em;
  }
}
```

### REM

* Le REM est basé sur la taille de la racine (soit la balise <html>) qui, par défaut a une valeur de 16px. Afin d'éviter tout calcul, il est nécessaire de l'écrasser en donnant une base de 10px soit 62.5%
* Le REM est intéressant à utiliser si les média-queries employées sont en REM également. Cela vous permettra de garder des propositions égales lorsqu'on va redimensionnner la page.
* Ses proportions seront également gardés quand l'utilisateur zommera dans votre page.

```css
html {
  font-size: 62.5%;
}
.mainTitle {
  /*1.6rem = 16px*/
  font-size: 1.6rem;
  /*32rem == 320px*/
  width: 32rem;
}
```

### VW(idth) / Vh(eight)

* Unités relatives à la taille de votre écran (peu importe le device)
* Attention au Vh et à son contenu. 100Vh = 100Vh quoi qu'il arrive.
* Vw : très utile pour les interfacs fluides.

##Liens utiles :

* https://Caniuse.com
* https://github.com/h5bp/Front-end-Developer-Interview-Questions
* http://cssnext.io/
