<!-- # = h1 -->

# Documentation

<!-- ## = h2 -->

## Convention BEM

- B --> Block
- E --> Element
- M --> Modifier

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

- Relative à la taille de son parent direct.

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

- Le REM est basé sur la taille de la racine (soit la balise <html>) qui, par défaut a une valeur de 16px. Afin d'éviter tout calcul, il est nécessaire de l'écrasser en donnant une base de 10px soit 62.5%
- Le REM est intéressant à utiliser si les média-queries employées sont en REM également. Cela vous permettra de garder des propositions égales lorsqu'on va redimensionnner la page.
- Ses proportions seront également gardés quand l'utilisateur zommera dans votre page.

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

- Unités relatives à la taille de votre écran (peu importe le device)
- Attention au Vh et à son contenu. 100Vh = 100Vh quoi qu'il arrive.
- Vw : très utile pour les interfacs fluides.

### Flexboxgrid

Les modificateurs réactifs permettent de spécifier différentes tailles de colonnes, décalages, alignement et distribution aux largeurs de la fenêtre xs, sm, md & lg

```html
  <div class="row">
      <div class="col-xs-12
                  col-sm-8
                  col-md-6
                  col-lg-4">
          <div class="box">Responsive</div>
      </div>
  </div>
```

```css
    voir flexboxgrid.min.css
```

# Flexbox Grid

[flexboxgrid.com](http://flexboxgrid.com)

Grid based on the `flex` display property.

## Install

### npm

`npm i flexboxgrid --save`

### bower

`bower install flexboxgrid`

### cdn

<code>CDNJS</code>

```html
<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/flexboxgrid/6.3.1/flexboxgrid.min.css" type="text/css" >
```

### css

- [Development](https://raw.githubusercontent.com/kristoferjoseph/flexboxgrid/master/dist/flexboxgrid.css)
- [Production](https://raw.githubusercontent.com/kristoferjoseph/flexboxgrid/master/dist/flexboxgrid.min.css)

Add the `flexboxgrid.css` **development** or `flexboxgrid.min.css` **production** to your html page.

```html
<link rel="stylesheet" href="css/flexboxgrid.min.css" type="text/css">
```

## Inspiration

- [topcoat-grid](https://github.com/topcoat/grid)
- [flexbox-grid by @zeMicro](https://github.com/zeMirco/flexbox-grid)
- [ptb2.me/flexgrid](http://ptb2.me/flexgrid/)
- [codepen.io/marcolago/pen/lqGFb](http://codepen.io/marcolago/pen/lqGFb)
- [philipwalton.github.io/solved-by-flexbox/demos/grids](http://philipwalton.github.io/solved-by-flexbox/demos/grids/)
- [davidwalsh.name/stylus-grid](http://davidwalsh.name/stylus-grid)

### Parcel Starter

- https://github.com/davidvenin/parcel-starter

## Composition du Starter front-end

Parcel + Babel (ES6+) + SASS = 🔥🔥🔥🔥

Simple front-end boilerplate and Javascript bundlers with <a href="https://github.com/parcel-bundler">Parcel</a> and CSS preprocessing with <a href="https://github.com/sass/sass">Sass</a>.

## Installation

Clone le répo

```
$ git clone https://github.com/davidvenin/parcel-starter.git
```

Installer les dépendances et lancé start script

```
$ npm install
$ npm start OR parcel index.html
```

Ouvrir le projet sur l'url `http://localhost:1234/`

## Overview

#### Structure du dossier Starter Parcel

```
    |-- index.html
    |-- app.js // Main application bundler
    |-- .postcssrc // Parcel configuration
    |-- src
        |-- scss
            |-- common.scss
        |-- js
            |-- [...]
```

### MySQL commandes & requêtes

## Commands

Access monitor: `mysql -u [username] -p;` (will prompt for password)

Show all databases: `show databases;`

Access database: `mysql -u [username] -p [database]` (will prompt for password)

Create new database: `create database [database];`

Select database: `use [database];`

Determine what database is in use: `select database();`

Show all tables: `show tables;`

Show table structure: `describe [table];`

List all indexes on a table: `show index from [table];`

Create new table with columns: `CREATE TABLE [table] ([column] VARCHAR(120), [another-column] DATETIME);`

Adding a column: `ALTER TABLE [table] ADD COLUMN [column] VARCHAR(120);`

Adding a column with an unique, auto-incrementing ID: `ALTER TABLE [table] ADD COLUMN [column] int NOT NULL AUTO_INCREMENT PRIMARY KEY;`

Inserting a record: `INSERT INTO [table] ([column], [column]) VALUES ('[value]', [value]');`

MySQL function for datetime input: `NOW()`

Selecting records: `SELECT * FROM [table];`

Explain records: `EXPLAIN SELECT * FROM [table];`

Selecting parts of records: `SELECT [column], [another-column] FROM [table];`

Counting records: `SELECT COUNT([column]) FROM [table];`

Counting and selecting grouped records: `SELECT *, (SELECT COUNT([column]) FROM [table]) AS count FROM [table] GROUP BY [column];`

Selecting specific records: `SELECT * FROM [table] WHERE [column] = [value];` (Selectors: `<`, `>`, `!=`; combine multiple selectors with `AND`, `OR`)

Select records containing `[value]`: `SELECT * FROM [table] WHERE [column] LIKE '%[value]%';`

Select records starting with `[value]`: `SELECT * FROM [table] WHERE [column] LIKE '[value]%';`

Select records starting with `val` and ending with `ue`: `SELECT * FROM [table] WHERE [column] LIKE '[val_ue]';`

Select a range: `SELECT * FROM [table] WHERE [column] BETWEEN [value1] and [value2];`

Select with custom order and only limit: `SELECT * FROM [table] WHERE [column] ORDER BY [column] ASC LIMIT [value];` (Order: `DESC`, `ASC`)

Updating records: `UPDATE [table] SET [column] = '[updated-value]' WHERE [column] = [value];`

Deleting records: `DELETE FROM [table] WHERE [column] = [value];`

Delete _all records_ from a table (without dropping the table itself): `DELETE FROM [table];`
(This also resets the incrementing counter for auto generated columns like an id column.)

Delete all records in a table: `truncate table [table];`

Removing table columns: `ALTER TABLE [table] DROP COLUMN [column];`

Deleting tables: `DROP TABLE [table];`

Deleting databases: `DROP DATABASE [database];`

Custom column output names: `SELECT [column] AS [custom-column] FROM [table];`

Export a database dump (more info [here](http://stackoverflow.com/a/21091197/1815847)): `mysqldump -u [username] -p [database] > db_backup.sql`

Use `--lock-tables=false` option for locked tables (more info [here](http://stackoverflow.com/a/104628/1815847)).

Import a database dump (more info [here](http://stackoverflow.com/a/21091197/1815847)): `mysql -u [username] -p -h localhost [database] < db_backup.sql`

Logout: `exit;`

## Aggregate functions

Select but without duplicates: `SELECT distinct name, email, acception FROM owners WHERE acception = 1 AND date >= 2015-01-01 00:00:00`

Calculate total number of records: `SELECT SUM([column]) FROM [table];`

Count total number of `[column]` and group by `[category-column]`: `SELECT [category-column], SUM([column]) FROM [table] GROUP BY [category-column];`

Get largest value in `[column]`: `SELECT MAX([column]) FROM [table];`

Get smallest value: `SELECT MIN([column]) FROM [table];`

Get average value: `SELECT AVG([column]) FROM [table];`

Get rounded average value and group by `[category-column]`: `SELECT [category-column], ROUND(AVG([column]), 2) FROM [table] GROUP BY [category-column];`

## Multiple tables

Select from multiple tables: `SELECT [table1].[column], [table1].[another-column], [table2].[column] FROM [table1], [table2];`

Combine rows from different tables: `SELECT * FROM [table1] INNER JOIN [table2] ON [table1].[column] = [table2].[column];`

Combine rows from different tables but do not require the join condition: `SELECT * FROM [table1] LEFT OUTER JOIN [table2] ON [table1].[column] = [table2].[column];` (The left table is the first table that appears in the statement.)

Rename column or table using an _alias_: `SELECT [table1].[column] AS '[value]', [table2].[column] AS '[value]' FROM [table1], [table2];`

## Users functions

List all users: `SELECT User,Host FROM mysql.user;`

Create new user: `CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';`

Grant `ALL` access to user for `*` tables: `GRANT ALL ON database.* TO 'user'@'localhost';`

## Find out the IP Address of the Mysql Host

`SHOW VARIABLES WHERE Variable_name = 'hostname';` ([source](http://serverfault.com/a/129646))

### Git commandes & Info

# Github

## Rappel

**Ne pas oublier la base : l'aide en ligne de commande.
Il s'agit de la meilleur documentation.**

```shell
git help config
git help push
git help pull
git help branch
```

## Configuration

```shell
# Identity Name
git config --global user.name "aquelito"

# Identity Email
git config --global user.email "axel@aquelito.fr"

# Editor Tool
git config --global core.editor subl

# Diff Tool
git config --global merge.tool filemerge
```

Liste des globals

```shell
git config --list
```

## Principales commandes

Status des fichiers

```shell
git status
```

Lister les branchs

```shell
git branch -a
```

`*`sur la branche courante.

Créer une branch

```shell
# Deux lignes: créer et basculer sur la nouvelle branch
git branch nom_de_ma_branch_nouvelle
git checkout nom_de_ma_branch_nouvelle

# Une seule ligne: créer et basculer
git checkout -b nom_de_ma_branch_nouvelle
```

Supprimer une branch

```shell
# Si la branch est local et n'est pas créée sur le repo distant
git branch -d nom_de_ma_branch_local

# Si la branch est présente sur le repo distant
git push origin --delete nom_de_ma_branch_distante
```

Changer de branch

```shell
git checkout nom_de_ma_branch
```

Premier commit

```shell
git add .
git commit -m "initial commit"
```

Commit suivant

```shell
git add chemin_vers_mon_fichier
git commit -m "message du commit"
```

Annuler le dernier commit et modifs

```shell
git reset --hard md5_commit
git push --force
```

Antidaté un commit.

```shell
git add .
GIT_AUTHOR_DATE="2015-12-12 08:32 +100" git commit -m "Commit antidaté"
```

Mettre à jour le dépôt local

```shell
git pull
```

Mettre à jour le dépôt local d'une branch spécifique

```shell
git pull origin MA_BRANCH
```

Envoyer ses commits vers le dépôt distant

```shell
git push
```

Envoyer ses commits vers le dépôt distant sur une branch spécifique

```shell
git push origin MA_BRANCH
```

Supprimer un fichier du répertoire de travail et de l'index

```shell
git rm nom_du_fichier
```

Supprimer un fichier de l'index

```shell
git rmg --cached nom_du_fichier
```

## Diff

```shell
# Affiche la différence entre le contenu du dernier commit et celui du
# répertoire de travail. Cela correspond à ce qui serait commité par git commit -a.
git diff HEAD

# Affiche la différence entre le contenu pointé par A et celui pointé par B.
git diff A B

# Diff entre un dossier présent sur deux branches
git diff master..MA_BRANCH chemin/vers/mon_dossier
```

## Log

```shell
# Classique
git log

# Affiche X derniers commits
git log -n X

# Affiche les commits concernant un dossier
git log --oneline -- chemin/vers/mon_dossier

# Affiche un ensemble de commits par date
git log --since=date --until=date

# Représentation de l’historique à partir de HEAD (commit / branch)
git log --oneline --graph --decorate

# Représentation de l’historique à partir d'un fichier (commit / branch)
git log --oneline --graph --decorate nom_du_fichier
```

## Annuler commits (soft)

Seul le commit est retiré de Git ; vos fichiers, eux, restent modifiés. Vous pouvez alors à nouveau changer vos fichiers si besoin est et refaire un commit.

Annuler le dernier commit

```shell
git reset HEAD^
```

Pour indiquer à quel commit on souhaite revenir, il existe plusieurs notations :

- HEAD : dernier commit ;
- HEAD^ : avant-dernier commit ;
- HEAD^^ : avant-avant-dernier commit ;
- HEAD~2 : avant-avant-dernier commit (notation équivalente) ;
- d6d98923868578a7f38dea79833b56d0326fcba1 : indique un numéro de commit ;
- d6d9892 : indique un numéro de commit version courte.

## Annuler commits (hard)

Si vous voulez annuler votre dernier commit et les changements effectués dans les fichiers, il faut faire un reset hard. _Cela annulera sans confirmation tout votre travail !_

Annuler les commits et perdre tous les changements

```shell
git reset --hard HEAD^
```

_Annuler les modifications d’un fichier avant un commit_

Si vous avez modifié plusieurs fichiers mais que vous n’avez pas encore envoyé le commit et que vous voulez restaurer un fichier tel qu’il était au dernier commit :

```shell
git checkout nom_du_fichier
```

_Annuler/Supprimer un fichier avant un commit_

Supposer que vous venez d’ajouter un fichier à Git avec `git add` et que vous vous apprêtez à le « commiter ». Cependant, vous vous rendez compte que ce fichier est une mauvaise idée et vous voulez annuler votre `git add`.

Il est possible de retirer un fichier qui avait été ajouté pour être « commité » en procédant comme suit :

```shell
git reset HEAD -- nom_du_fichier_a_supprimer
```

### Liens utiles :

- https://Caniuse.com
- https://github.com/h5bp/Front-end-Developer-Interview-Questions
- http://cssnext.io/
- http://flexboxgrid.com
- https://github.com/sass/sass
