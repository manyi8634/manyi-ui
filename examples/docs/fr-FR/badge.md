## Badge

Un nombre ou un status affiché par-dessus un bouton ou un icône.

### Usage

Affiche le nombre de nouveaux messages.

:::demo La quantité est définit par `value` qui accepte un `Number` ou un `String`.

```html
<my-badge :value="12" class="item">
  <my-button size="small">Commentaires</my-button>
</my-badge>
<my-badge :value="3" class="item">
  <my-button size="small">Réponses</my-button>
</my-badge>
<my-badge :value="1" class="item" type="primary">
  <my-button size="small">Commentaires</my-button>
</my-badge>
<my-badge :value="2" class="item" type="warning">
  <my-button size="small">Réponses</my-button>
</my-badge>

<my-dropdown trigger="click">
  <span class="el-dropdown-link">
    Cliquez<i class="el-icon-caret-bottom el-icon--right"></i>
  </span>
  <my-dropdown-menu slot="dropdown">
    <my-dropdown-item class="clearfix">
      Commentaires
      <my-badge class="mark" :value="12" />
    </my-dropdown-item>
    <my-dropdown-item class="clearfix">
      Réponses
      <my-badge class="mark" :value="3" />
    </my-dropdown-item>
  </my-dropdown-menu>
</my-dropdown>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Valeur maximale

Vous pouvez configurer la valeur maximale.

:::demo La valeur maximale est définit par `max` qui accepte un `Number`. Ceci ne marche qui si `value` est également un `Number`.

```html
<my-badge :value="200" :max="99" class="item">
  <my-button size="small">Commentaires</my-button>
</my-badge>
<my-badge :value="100" :max="10" class="item">
  <my-button size="small">Réponses</my-button>
</my-badge>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Configuration

Affiche du texte autre que des nombres.

:::demo Quand `value` est un `String`, il affiche un texte personnalisé.

```html
<my-badge value="new" class="item">
  <my-button size="small">Commentaires</my-button>
</my-badge>
<my-badge value="hot" class="item">
  <my-button size="small">Réponses</my-button>
</my-badge>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Point rouge

Utilisez un point rouge pour signaler du contenu devant être remarqué.

:::demo Utilisez l'attribut `is-dot` qui est un `Boolean`.

```html
<my-badge is-dot class="item">Requète</my-badge>
<my-badge is-dot class="item">
  <my-button class="share-button" icon="el-icon-share" type="primary"></my-button>
</my-badge>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Attributs

| Attribut     | Description     | Type            | Valeurs acceptées       | Défaut |
|-------------  |---------------- |---------------- |---------------------- |-------- |
| value         | Valeur affichée.   | string, number  |          —            |    —    |
| max           |  Valeur maximale, affiche '{max}+' quand elle est dépassée. Ne marche que si `value` est un `Number`.   | number  |         —              |     —    |
| is-dot        | Affiche un point rouge. | boolean   |    —           |  false  |
| hidden        | Cache le badge.    | boolean         |          —            |  false  |
| type          | Type du bouton.     | string          | primary / success / warning / danger / info |   —  |
