## Link

Un hyperlien textuel.

### Usage basique

Lien texte basique.

:::demo

```html
<div>
  <my-link href="https://element.eleme.io" target="_blank">défaut</my-link>
  <my-link type="primary">primaire</my-link>
  <my-link type="success">succès</my-link>
  <my-link type="warning">avertissement</my-link>
  <my-link type="danger">danger</my-link>
  <my-link type="info">info</my-link>
</div>
```

:::

### Désactivé

Lien désactivé.

:::demo

```html
<div>
  <my-link disabled>défaut</my-link>
  <my-link type="primary" disabled>primaire</my-link>
  <my-link type="success" disabled>succès</my-link>
  <my-link type="warning" disabled>avertissement</my-link>
  <my-link type="danger" disabled>danger</my-link>
  <my-link type="info" disabled>info</my-link>
</div>
```

:::

### Souligné

Lien souligné.

:::demo

```html
<div>
  <my-link :underline="false">non souligné</my-link>
  <my-link>Souligné</my-link>
</div>
```

:::

### Icône

Lien avec icône.

:::demo

```html
<div>
  <my-link icon="el-icon-edit">Éditer</my-link>
  <my-link>Vérifier<i class="el-icon-view el-icon--right"></i> </my-link>
</div>
```

:::

### Attributs

| Attribut  | Description                     | Type    | Options                                     | Défaut  |
| --------- | ------------------------------- | ------- | ------------------------------------------- | ------- |
| type      | Type du lien.                   | string  | primary / success / warning / danger / info | défaut  |
| underline | Si le composant est souligné.   | boolean | —                                           | true    |
| disabled  | Si le composant est désactivé.  | boolean | —                                           | false   |
| href      | Identique au `href` natif.      | string  | —                                           | -       |
| icon      | Nom de classe de l'icône.       | string  | —                                           | -       |
