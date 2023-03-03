## Breadcrumb

Muestra la localización de la página actual, haciendo más fácil el poder ir a la página anterior.

### Uso básico


:::demo En `el-breadcrumb`, cada `el-breadcrumb-item` es un tag que representa cada nivel empezando desde la homepage. Este componente tiene un atributo `String` llamado `separator`, el mismo determina el carácter separador. El valor por defecto es '/'.

```html
<my-breadcrumb separator="/">
  <my-breadcrumb-item :to="{ path: '/' }">homepage</my-breadcrumb-item>
  <my-breadcrumb-item><a href="/">promotion management</a></my-breadcrumb-item>
  <my-breadcrumb-item>promotion list</my-breadcrumb-item>
  <my-breadcrumb-item>promotion detail</my-breadcrumb-item>
</my-breadcrumb>
```
:::

### Icono separador

:::demo Setee `separator-class` para que utilice `iconfont` como separador，el mismo va a cubrir `separator`

```html
<my-breadcrumb separator-class="el-icon-arrow-right">
  <my-breadcrumb-item :to="{ path: '/' }">homepage</my-breadcrumb-item>
  <my-breadcrumb-item>promotion management</my-breadcrumb-item>
  <my-breadcrumb-item>promotion list</my-breadcrumb-item>
  <my-breadcrumb-item>promotion detail</my-breadcrumb-item>
</my-breadcrumb>
```
:::

### Breadcrumb atributos
| Atributo        | Descripción                            | Tipo   | Valores aceptados | Por defecto |
| --------------- | -------------------------------------- | ------ | ----------------- | ----------- |
| separator       | carácter separador                     | string | —                 | /           |
| separator-class | nombre de la clase del icono separador | string | —                 | -           |

### Breadcrumb Item atributos
| Atributo | Descripción                              | Tipo          | Valores aceptados | Por defecto |
| -------- | ---------------------------------------- | ------------- | ----------------- | ----------- |
| to       | ruta del link, lo mismo que `to` de `vue-router` | string/object | —                 | —           |
| replace  | si `true`,  la navegación no dejara una entrada en la historia | boolean       | —                 | false       |





