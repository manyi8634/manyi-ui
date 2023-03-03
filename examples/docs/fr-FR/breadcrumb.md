## Breadcrumb

Affiche le chemin de la page actuelle, afin de pouvoir naviguer plus facilement.

### Usage


:::demo Dans `el-breadcrumb`, chaque `el-breadcrumb-item` est un tag représentant chaque niveau depuis la page d'accueil. Ce Composant possède un attribut de type `String` appelé `separator` qui détermine le séparateur. Sa valeur par défaut est '/'.

```html
<my-breadcrumb separator="/">
  <my-breadcrumb-item :to="{ path: '/' }">Accueil</my-breadcrumb-item>
  <my-breadcrumb-item><a href="/">Gestion promotions</a></my-breadcrumb-item>
  <my-breadcrumb-item>Liste promotions</my-breadcrumb-item>
  <my-breadcrumb-item>Détail promotion</my-breadcrumb-item>
</my-breadcrumb>
```
:::

### Icône de séparation

:::demo Configurez `separator-class` pour utiliser `iconfont` en tant que séparateur. Cela remplacera `separator`.

```html
<my-breadcrumb separator-class="el-icon-arrow-right">
  <my-breadcrumb-item :to="{ path: '/' }">Accueil</my-breadcrumb-item>
  <my-breadcrumb-item>Gestion promotions</my-breadcrumb-item>
  <my-breadcrumb-item>Liste promotions</my-breadcrumb-item>
  <my-breadcrumb-item>Détail promotion</my-breadcrumb-item>
</my-breadcrumb>
```
:::

### Attributs de Breadcrumb
| Attributs      | Description          | Type      | Valeurs acceptées            | Défaut|
|---------- |-------------- |---------- |--------------------------------  |-------- |
| separator | Caractère de séparation | string | — | / |
| separator-class | Classe de l'icône de séparation | string | — | - |

### Attributs de Breadcrumb Item
| Attributs      | Description          | Type      | Valeurs acceptées            | Défaut|
|---------- |-------------- |---------- |--------------------------------  |-------- |
| to | Route cible du lien, identique au `to` de `vue-router`. | string/object | — | — |
| replace | Si `true`, la navigation ne laissera pas d'historique. | boolean | — | false |
