## PageHeader

Si la ruta de la página es simple, se recomienda utilizar  PageHeader en lugar de Breadcrumb.

### Básico

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

### Atributos
| Atributos | Descripción | Tipo   | Valores aceptados | Por defecto |
|---------- |-------------- |---------- |------------------------------ | ------ |
| title     | titulo principal | string    |  —                            | Back   |
| content   | contenido   | string    |  —                            | —      |

### Eventos
| Nombre evento | Descripción | Parámetros |
|----------- |-------------- |----------- |
| back       | se activa cuando se hace clic en el lado derecho | — |

### Slots
| Nombre del slot | Descripción |
| --------------- | ----------- |
| title           | titulo      |
| content         | contenido   |
