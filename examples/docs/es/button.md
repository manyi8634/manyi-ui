## Button

Botones comúnmente usados.

### Uso básico

:::demo Use `type`, `plain`,`round` y `circle` para definir estilos a los botones.

```html
<my-row>
  <my-button>Default</my-button>
  <my-button type="primary">Primary</my-button>
  <my-button type="success">Success</my-button>
  <my-button type="info">Info</my-button>
  <my-button type="warning">Warning</my-button>
  <my-button type="danger">Danger</my-button>
</my-row>

<my-row>
  <my-button plain>Plain</my-button>
  <my-button type="primary" plain>Primary</my-button>
  <my-button type="success" plain>Success</my-button>
  <my-button type="info" plain>Info</my-button>
  <my-button type="warning" plain>Warning</my-button>
  <my-button type="danger" plain>Danger</my-button>
</my-row>

<my-row>
  <my-button round>Round</my-button>
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

### Botón deshabilitado

El atributo `disabled` determina su un botón esta deshabilitado.

:::demo Use el atributo `disabled` para determinar si un botón esta deshabilitado. Acepta un valor `Boolean`.

```html
<my-row>
  <my-button disabled>Default</my-button>
  <my-button type="primary" disabled>Primary</my-button>
  <my-button type="success" disabled>Success</my-button>
  <my-button type="info" disabled>Info</my-button>
  <my-button type="warning" disabled>Warning</my-button>
  <my-button type="danger" disabled>Danger</my-button>
</my-row>

<my-row>
  <my-button plain disabled>Plain</my-button>
  <my-button type="primary" plain disabled>Primary</my-button>
  <my-button type="success" plain disabled>Success</my-button>
  <my-button type="info" plain disabled>Info</my-button>
  <my-button type="warning" plain disabled>Warning</my-button>
  <my-button type="danger" plain disabled>Danger</my-button>
</my-row>
```
:::

### Botón de texto

Botones sin borde ni fondo.

:::demo
```html
<my-button type="text">Text Button</my-button>
<my-button type="text" disabled>Text Button</my-button>
```
:::

### Botón icono

Use iconos para darle mayor significado a Button. Se puede usar simplemente un icono o un icono con texto.

:::demo Use el atributo `icon` para agregar un icono. Puede encontrar el listado de iconos en el componente de iconos. Agregar iconos a la derecha del texto se puede conseguir con un tag `<i>`. También se pueden usar iconos personalizados.

```html
<my-button type="primary" icon="el-icon-edit"></my-button>
<my-button type="primary" icon="el-icon-share"></my-button>
<my-button type="primary" icon="el-icon-delete"></my-button>
<my-button type="primary" icon="el-icon-search">Search</my-button>
<my-button type="primary">Upload<i class="el-icon-upload el-icon-right"></i></my-button>
```
:::

### Grupo de botones

Mostrar un grupo de botones puede ser usado para mostrar un grupo de operaciones similares.

:::demo Use el tag `<my-button-group>` para agrupar sus botones.

```html
<my-button-group>
  <my-button type="primary" icon="el-icon-arrow-left">Previous Page</my-button>
  <my-button type="primary">Next Page<i class="el-icon-arrow-right el-icon-right"></i></my-button>
</my-button-group>
<my-button-group>
  <my-button type="primary" icon="el-icon-edit"></my-button>
  <my-button type="primary" icon="el-icon-share"></my-button>
  <my-button type="primary" icon="el-icon-delete"></my-button>
</my-button-group>
```
:::

### Botón de descarga 

Cuando se hace clic en un botón para descargar datos, el botón muestra un estado de descarga.

:::demo Ajuste el atributo `loading` a `true` para mostrar el estado de descarga.

```html
<my-button type="primary" :loading="true">Loading</my-button>
```
:::

### Tamaños

Además del tamaño por defecto, el componente Button provee tres tamaños adicionales para utilizar en diferentes escenarios.

:::demo Use el atributo `size` para setear tamaños adicionales con `medium`, `small` o `mini`.

```html
<my-row>
  <my-button>Default</my-button>
  <my-button size="medium">Medium</my-button>
  <my-button size="small">Small</my-button>
  <my-button size="mini">Mini</my-button>
</my-row>
<my-row>
  <my-button round>Default</my-button>
  <my-button size="medium" round>Medium</my-button>
  <my-button size="small" round>Small</my-button>
  <my-button size="mini" round>Mini</my-button>
</my-row>
```
:::

### Atributos
| Atributo    | Descripción                                   | Tipo    | Valores aceptados                                  | Por defecto |
| ----------- | --------------------------------------------- | ------- | -------------------------------------------------- | ----------- |
| size        | tamaño del botón                              | string  | medium / small / mini                              | —           |
| type        | tipo de botón                                 | string  | primary / success / warning / danger / info / text | —           |
| plain       | determinar si es o no un botón plano          | boolean | —                                                  | false       |
| round       | determinar si es o no un botón redondo        | boolean | —                                                  | false       |
| circle      | determina si es un botón circular             | boolean | —                                                  | false       |
| loading     | determinar si es o no un botón de descarga    | boolean | —                                                  | false       |
| disabled    | deshabilitar el botón                         | boolean | —                                                  | false       |
| icon        | nombre de la clase del icono                  | string  | —                                                  | —           |
| autofocus   | misma funcionalidad que la nativa `autofocus` | boolean | —                                                  | false       |
| native-type | misma funcionalidad que la nativa `type`      | string  | button / submit / reset                            | button      |

