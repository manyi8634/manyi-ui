## Badge

Marcas en forma de número o estado para botones e iconos.

### Uso básico

Muestra la cantidad de mensajes nuevos.

:::demo La cantidad está definida por `value` que acepta `Number` o `String`.

```html
<my-badge :value="12" class="item">
  <my-button size="small">comments</my-button>
</my-badge>
<my-badge :value="3" class="item">
  <my-button size="small">replies</my-button>
</my-badge>
<my-badge :value="1" class="item" type="primary">
  <my-button size="small">comments</my-button>
</my-badge>
<my-badge :value="2" class="item" type="warning">
  <my-button size="small">replies</my-button>
</my-badge>

<my-dropdown trigger="click">
  <span class="el-dropdown-link">
    Click Me<i class="el-icon-caret-bottom el-icon--right"></i>
  </span>
  <my-dropdown-menu slot="dropdown">
    <my-dropdown-item class="clearfix">
      comments
      <my-badge class="mark" :value="12" />
    </my-dropdown-item>
    <my-dropdown-item class="clearfix">
      replies
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

### Valor máximo

Se puede personalizar el valor máximo.

:::demo El valor máximo se define como `max` el cual es un `Number`. Nota: solo funciona si `value` es también un `Number`.

```html
<my-badge :value="200" :max="99" class="item">
  <my-button size="small">comments</my-button>
</my-badge>
<my-badge :value="100" :max="10" class="item">
  <my-button size="small">replies</my-button>
</my-badge>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Personalizaciones

Mostrar texto en vez de números.

:::demo Cuando `value` es un `String`, puede mostrar texto personalizado.

```html
<my-badge value="new" class="item">
  <my-button size="small">comments</my-button>
</my-badge>
<my-badge value="hot" class="item">
  <my-button size="small">replies</my-button>
</my-badge>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Pequeño punto rojo

Puede utilizar un punto rojo para marcar contenido que debe ser notado.

:::demo Use el atributo `is-dot`. Es un `Boolean`.

```html
<my-badge is-dot class="item">query</my-badge>
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

### Atributos
| Atributo | Descripción                              | Tipo           | Valores aceptados | Por defecto |
| -------- | ---------------------------------------- | -------------- | ----------------- | ----------- |
| value    | valor a mostrar                          | string, number | —                 | —           |
| max      | valor máximo, Muestra '{max}+' cuando se excede. Solo funciona si `value` es un `Number` | number         | —                 | —           |
| is-dot   | si se debe mostrar un pequeño punto      | boolean        | —                 | false       |
| hidden   | oculta el badge                    | boolean        | —                 | false       |
| type     | tipo de botón                            | string         | primary / success / warning / danger / info | — |

