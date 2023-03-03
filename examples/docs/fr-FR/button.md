## Bouton

Bouton communément utilisé.

### Usage

:::demo Utilisez `type`, `plain`, `round` et `circle` pour définir le style du bouton.

```html
<my-row>
  <my-button>Défaut</my-button>
  <my-button type="primary">Primary</my-button>
  <my-button type="success">Success</my-button>
  <my-button type="info">Info</my-button>
  <my-button type="warning">Warning</my-button>
  <my-button type="danger">Danger</my-button>
</my-row>

<my-row>
  <my-button plain>Plein</my-button>
  <my-button type="primary" plain>Primary</my-button>
  <my-button type="success" plain>Success</my-button>
  <my-button type="info" plain>Info</my-button>
  <my-button type="warning" plain>Warning</my-button>
  <my-button type="danger" plain>Danger</my-button>
</my-row>

<my-row>
  <my-button round>Arrondi</my-button>
  <my-button type="primary" round>Primary</my-button>
  <my-button type="success" round>Success</my-button>
  <my-button type="info" round>Info</my-button>
  <my-button type="warning" round>Warning</my-button>
  <my-button type="danger" round>Danger</my-button>
</my-row>

<my-row>
  <my-button icon="el-icon-search" circle></my-button>
  <my-button type="primary" icon="el-icon-edit" circle></my-button>
  <my-button type="success" icon="el-icon-check" circle></my-button>
  <my-button type="info" icon="el-icon-message" circle></my-button>
  <my-button type="warning" icon="el-icon-star-off" circle></my-button>
  <my-button type="danger" icon="el-icon-delete" circle></my-button>
</my-row>
```
:::

### Bouton désactivé

L'attribut `disabled` détermine si le bouton est désactivé.

:::demo Utilisez l'attribut `disabled` pour déterminer si un bouton est désactivé ou non. Il accepte un `Boolean`.

```html
<my-row>
  <my-button disabled>Défaut</my-button>
  <my-button type="primary" disabled>Principal</my-button>
  <my-button type="success" disabled>Succès</my-button>
  <my-button type="info" disabled>Info</my-button>
  <my-button type="warning" disabled>Attention</my-button>
  <my-button type="danger" disabled>Danger</my-button>
</my-row>

<my-row>
  <my-button plain disabled>Plein</my-button>
  <my-button type="primary" plain disabled>Principal</my-button>
  <my-button type="success" plain disabled>Succès</my-button>
  <my-button type="info" plain disabled>Info</my-button>
  <my-button type="warning" plain disabled>Attention</my-button>
  <my-button type="danger" plain disabled>Danger</my-button>
</my-row>
```
:::

### Bouton texte

Bouton sans bordure ni fond.

:::demo
```html
<my-button type="text">Bouton texte</my-button>
<my-button type="text" disabled>Bouton texte</my-button>
```
:::

### Icône

Utilisez des icônes pour ajouter plus de sens aux boutons. Vous pouvez utiliser uniquement l'icône pour économiser de l'espace, ou bien l'utiliser avec du texte.

:::demo Utilisez l'attribut `icon` pour ajouter une icône. Vous pourrez trouver la liste des icônes dans le composant Icon d'Element. Ajouter des icônes sur le coté droit du texte est possible grâce à la balise `<i>`. Des icônes personnalisées peuvent également être utilisées.

```html
<my-button type="primary" icon="el-icon-edit"></my-button>
<my-button type="primary" icon="el-icon-share"></my-button>
<my-button type="primary" icon="el-icon-delete"></my-button>
<my-button type="primary" icon="el-icon-search">Recherche</my-button>
<my-button type="primary">Upload<i class="el-icon-upload el-icon-right"></i></my-button>
```
:::

### Groupes de boutons

Affiche un groupe de bouton. Peut être utilisé pour grouper un ensemble d'opérations similaires.

:::demo Utilisez la balise `<my-button-group>` pour grouper vos boutons.

```html
<my-button-group>
  <my-button type="primary" icon="el-icon-arrow-left">Page précédente</my-button>
  <my-button type="primary">Page suivante<i class="el-icon-arrow-right el-icon-right"></i></my-button>
</my-button-group>
<my-button-group>
  <my-button type="primary" icon="el-icon-edit"></my-button>
  <my-button type="primary" icon="el-icon-share"></my-button>
  <my-button type="primary" icon="el-icon-delete"></my-button>
</my-button-group>
```
:::

### Bouton en chargement

Cliquez sur le bouton pour charger des données et il affichera un état de chargement.

:::demo Configurez l'attribut `loading` à `true` pour afficher un état de chargement.

```html
<my-button type="primary" :loading="true">Chargement</my-button>
```
:::

### Tailles

En plus de la taille par défaut, le composant Button fournit trois tailles supplémentaires pour différents scénarios.

:::demo Utilisez l'attribut `size` pour choisir d'autres tailles parmi `medium`, `small` ou `mini`.

```html
<my-row>
  <my-button>Défaut</my-button>
  <my-button size="medium">Medium</my-button>
  <my-button size="small">Small</my-button>
  <my-button size="mini">Mini</my-button>
</my-row>
<my-row>
  <my-button round>Défaut</my-button>
  <my-button size="medium" round>Medium</my-button>
  <my-button size="small" round>Small</my-button>
  <my-button size="mini" round>Mini</my-button>
</my-row>
```
:::

### Attributs
| Attribut      | Description    | Type      | Valeurs acceptées       | Défaut   |
|---------- |-------- |---------- |-------------  |-------- |
| size     | Taille du bouton.   | string  |   medium / small / mini            |    —     |
| type     | Type du bouton.   | string    |   primary / success / warning / danger / info / text |     —    |
| plain     | Détermine si le bouton est plein.   | boolean    | — | false   |
| round     | Détermine si le bouton est arrondi.   | boolean    | — | false   |
| circle     | Détermine si le bouton est un cercle.   | boolean    | — | false   |
| loading   | Détermine si l'état de chargement est affiché.   | boolean    | — | false   |
| disabled  | Désactive le bouton    | boolean   | —   | false   |
| icon  | Classe de l'icône. | string   |  —  |  —  |
| autofocus  | Identique à l'attribut natif `autofocus` | boolean   |  —  |  false  |
| native-type | Identique à l'attribut natif `type` | string | button / submit / reset | button |
