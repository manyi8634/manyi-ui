## Steps

Permet de guider l'utilisateur dans l'accomplissement de toutes les taches d'un processus. Les étapes peuvent être créées de manière à refléter le scénario en question et leur nombre ne peut être inférieur à 2.

### Usage

Voici une barre d'étapes basique.

:::demo Réglez l'attribut `active` avec une variable `Number`, qui indique l'index des étapes et commence à 0. L'attribut `space` permet de déterminer si l'espace entre les étapes doit être fixe à l'aide d'un `Number`. L'unité de `space` est `px`. Si cet attribut est absent, la barre sera responsive. L'attribut `finish-status` change le statut d'accomplissement des étapes.

```html
<my-steps :active="active" finish-status="success">
  <my-step title="Étape 1"></my-step>
  <my-step title="Étape 2"></my-step>
  <my-step title="Étape 3"></my-step>
</my-steps>

<my-button style="margin-top: 12px;" @click="next">Prochaine étape</my-button>

<script>
  export default {
    data() {
      return {
        active: 0
      };
    },

    methods: {
      next() {
        if (this.active++ > 2) this.active = 0;
      }
    }
  }
</script>
```
:::

### Barre avec statut

Vous pouvez afficher le statut de chaque étape.

:::demo Utilisez `title` pour définir le nom de l'étape, ou écrasez cet attribut en utilisant un `slot`. La liste complète des slots se trouve en fin de page.

```html
<my-steps :space="200" :active="1" finish-status="success">
  <my-step title="Terminé"></my-step>
  <my-step title="En cours"></my-step>
  <my-step title="Étape 3"></my-step>
</my-steps>
```
:::

### Barre avec description

Vous pouvez ajouter une description pour chaque étape.

:::demo
```html
<my-steps :active="1">
  <my-step title="Étape 1" description="Une description"></my-step>
  <my-step title="Étape 2" description="Une description"></my-step>
  <my-step title="Étape 3" description="Une description"></my-step>
</my-steps>
```
:::

### Centrer

Le titre et la description peuvent être centrés.

:::demo
```html
<my-steps :active="2" align-center>
  <my-step title="Étape 1" description="Une description"></my-step>
  <my-step title="Étape 2" description="Une description"></my-step>
  <my-step title="Étape 3" description="Une description"></my-step>
  <my-step title="Étape 4" description="Une description"></my-step>
</my-steps>
```
:::

### Barre avec icône

Une grande variété d'icônes peut être utilisée dans la barre d'étapes.

:::demo L'icône est ajoutée en utilisant `icon`. Les types d'icônes possibles sont référencés dans la documentation du composant Icon. De plus, vous pouvez utilisé une icône personnalisée en utilisant un `slot`.

```html
<my-steps :active="1">
  <my-step title="Étape 1" icon="el-icon-edit"></my-step>
  <my-step title="Étape 2" icon="el-icon-upload"></my-step>
  <my-step title="Étape 3" icon="el-icon-picture"></my-step>
</my-steps>
```
:::

### Barre verticale

La barre d'étape peut être affichée de manière verticale.

:::demo Mettez simplement l'attribut `direction` à ` vertical` dans l'élément `el-steps`.

```html
<div style="height: 300px;">
  <my-steps direction="vertical" :active="1">
    <my-step title="Étape 1"></my-step>
    <my-step title="Étape 2"></my-step>
    <my-step title="Étape 3"></my-step>
  </my-steps>
</div>
```
:::

### Barre d'étapes simple

La barre peut être simplifiée de manière à ce que `align-center`, `description`, `direction` et `space` soient ignorées.

:::demo
```html

<my-steps :space="200" :active="1" simple>
  <my-step title="Étape 1" icon="el-icon-edit"></my-step>
  <my-step title="Étape 2" icon="el-icon-upload"></my-step>
  <my-step title="Étape 3" icon="el-icon-picture"></my-step>
</my-steps>

<my-steps :active="1" finish-status="success" simple style="margin-top: 20px">
  <my-step title="Étape 1" ></my-step>
  <my-step title="Étape 2" ></my-step>
  <my-step title="Étape 3" ></my-step>
</my-steps>
```
:::

### Attributs de la barre

| Attribut      | Description          | Type      | Valeurs acceptées       | Défaut  |
|---------- |-------- |---------- |-------------  |-------- |
| space | L'espace entre chaque étape, sera responsive si omis. Supporte les pourcentages. | number / string | — | — |
| direction | L'orientation de la barre. | string | vertical/horizontal | horizontal |
| active | L'index de l'étape courante.  | number | — | 0 |
| process-status | Le statut de l'étape courante. | string | wait / process / finish / error / success | process |
| finish-status | Le statut de la dernière étape. | string | wait / process / finish / error / success | finish |
| align-center | Si le titre et la description doivent être centrés. | boolean | — | false |
| simple | Si un thème simple doit être appliqué. | boolean | - | false |

### Attributs des étapes

| Attribut      | Description          | Type      | Valeurs acceptées       | Défaut  |
|---------- |-------- |---------- |-------------  |-------- |
| title | Titre de l'étape. | string | — | — |
| description | Description de l'étape. | string | — | — |
| icon | step icon | Classe de l'icône d'étape. Les icônes peuvent aussi être passées via des slots. | string | — |
| status | Le statut actuel. Sera déterminé par la barre d'étapes si omis. | wait / process / finish / error / success | - |

### Slots des étapes

| Nom | Description |
|----|----|
| icon | L'icône de l'étape. |
| title | Le titre de l'étape. |
| description | La description de l'étape. |
