## PageHeader

Si le chemin de la page est simple, il est recommandé d’utiliser PageHeader au lieu de Breadcrumb.

### Basic

:::demo
```html
<my-page-header @back="goBack" content="detail">
</my-page-header>

<script>
  export default {
    methods: {
      goBack() {
        console.log('go back');
      }
    }
  }
</script>
```
:::

### Attributes
| Attribute | Description   | Type      | Valeurs acceptées             | Défaut |
|---------- |-------------- |---------- |------------------------------ | ------ |
| title     | titre principal | string  |  —                            | Back   |
| content   | contenu       | string    |  —                            | —      |

### Events
| Event Name | Description   | Parameters |
|----------- |-------------- |----------- |
| back       | se déclenche lorsque vous cliquez sur le côté droit | — |

### Slots
| slot      | Description            |
|---------- | ---------------------- |
| title     | contenu du titre       |
| content   | contenu                |
