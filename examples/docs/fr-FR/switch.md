## Switch

Switch est utilisé pour choisir entre deux états opposés.

### Usage

:::demo Liez `v-model` à une variable de type `Boolean`. Les attributs `active-color` et `inactive-color` déterminent les couleurs des deux états.

```html
<my-switch v-model="value1">
</my-switch>
<my-switch
  v-model="value2"
  active-color="#13ce66"
  inactive-color="#ff4949">
</my-switch>

<script>
  export default {
    data() {
      return {
        value1: true,
        value2: true
      }
    }
  };
</script>
```
:::

### Description

:::demo Utilisez `active-text` et `inactive-text` pour afficher une description de chaque étape.

```html
<my-switch
  v-model="value1"
  active-text="Paiement mensuel"
  inactive-text="Paiement annuel">
</my-switch>
<my-switch
  style="display: block"
  v-model="value2"
  active-color="#13ce66"
  inactive-color="#ff4949"
  active-text="Paiement mensuel"
  inactive-text="Paiement annuel">
</my-switch>

<script>
  export default {
    data() {
      return {
        value1: true,
        value2: true
      }
    }
  };
</script>
```
:::

### Valeurs des états

:::demo Vous pouvez utiliser `active-value` et `inactive-value` pour déterminer la valeur de chaque état. Ils prennent un `Boolean`, `String` ou `Number`.

```html
<my-tooltip :content="'Valeur de l\'état: ' + value" placement="top">
  <my-switch
    v-model="value"
    active-color="#13ce66"
    inactive-color="#ff4949"
    active-value="100"
    inactive-value="0">
  </my-switch>
</my-tooltip>

<script>
  export default {
    data() {
      return {
        value: '100'
      }
    }
  };
</script>
```

:::

### Désactivé

:::demo Ajoutez l'attribut `disabled` pour désactiver le switch.

```html
<my-switch
  v-model="value1"
  disabled>
</my-switch>
<my-switch
  v-model="value2"
  disabled>
</my-switch>

<script>
  export default {
    data() {
      return {
        value1: true,
        value2: false
      }
    }
  };
</script>
```
:::

### Attributs

| Attribut      | Description          | Type      | Valeurs acceptées       | Défaut |
| ----| ----| ----| ----|---- |
| value / v-model | La valeur liée. | boolean / string / number | — | — |
| disabled | Si le switch est désactivé. | boolean | — | false |
| width | Largeur du switch. | number | — | 40 |
| active-icon-class | Classe de l'icône de l'état `on`, écrase `active-text`. | string | — | — |
| inactive-icon-class | Classe de l'icône de l'état `off`, écrase `inactive-text`. | string | — | — |
| active-text | Texte affiché dans l'état `on`. | string | — | — |
| inactive-text | Texte affiché dans l'état `off`. | string | — | — |
| active-value  | Valeur du switch dans l'état `on`. | boolean / string / number | — | true |
| inactive-value  | Valeur du switch dans l'état `off`. | boolean / string / number | — | false |
| active-color | Couleur de fond de l'état `on`. | string | — | #409EFF |
| inactive-color | Couleur de fond de l'état `off`. | string | — | #C0CCDA |
| name| Nom du champ d'input du switch. | string | — | — |
| validate-event | Si la validation doit avoir lieu. | boolean | - | true |

### Évènements

| Nom | Description | Paramètres |
| ---- | ----| ---- |
| change | Se déclenche quand la valeur change. | La valeur après changement. |

### Méthodes

| Méthode | Description | Paramètres |
|-------|--------|------- |
| focus | Donne le focus au switch. | — |
