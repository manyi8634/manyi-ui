## Tag

Se utiliza para marcar y seleccionar.

### Uso básico

:::demo Utilice el atributo `type` para definir el tipo de etiqueta. Además, el atributo `color` se puede utilizar para establecer el color de fondo de la etiqueta.

```html
<my-tag>Tag 1</my-tag>
<my-tag type="success">Tag 2</my-tag>
<my-tag type="info">Tag 3</my-tag>
<my-tag type="warning">Tag 4</my-tag>
<my-tag type="danger">Tag 5</my-tag>
```
:::

### Etiqueta removible

:::demo el atributo `closable` puede usarse para definir una etiqueta removible. Acepta un `Boolean`. De forma predeterminada, la eliminación de la etiqueta tiene una animación que se desvanece. Si no quiere usarlo, puede configurar el atributo `disable-transitions` , que acepta `Boolean`, como `true`. Se dispara el evento `close` cuando la etiqueta es removida. 

```html
<my-tag
  v-for="tag in tags"
  :key="tag.name"
  closable
  :type="tag.type">
  {{tag.name}}
</my-tag>

<script>
  export default {
    data() {
      return {
        tags: [
          { name: 'Tag 1', type: '' },
          { name: 'Tag 2', type: 'success' },
          { name: 'Tag 3', type: 'info' },
          { name: 'Tag 4', type: 'warning' },
          { name: 'Tag 5', type: 'danger' }
        ]
      };
    }
  }
</script>
```
:::

### Editar dinámicamente

Puede utilizar el evento `close` para añadir y eliminar etiquetas dinámicamente.

:::demo
```html
<my-tag
  :key="tag"
  v-for="tag in dynamicTags"
  closable
  :disable-transitions="false"
  @close="handleClose(tag)">
  {{tag}}
</my-tag>
<my-input
  class="input-new-tag"
  v-if="inputVisible"
  v-model="inputValue"
  ref="saveTagInput"
  size="mini"
  @keyup.enter.native="handleInputConfirm"
  @blur="handleInputConfirm"
>
</my-input>
<my-button v-else class="button-new-tag" size="small" @click="showInput">+ New Tag</my-button>

<style>
  .el-tag + .el-tag {
    margin-left: 10px;
  }
  .button-new-tag {
    margin-left: 10px;
    height: 32px;
    line-height: 30px;
    padding-top: 0;
    padding-bottom: 0;
  }
  .input-new-tag {
    width: 90px;
    margin-left: 10px;
    vertical-align: bottom;
  }
</style>

<script>
  export default {
    data() {
      return {
        dynamicTags: ['Tag 1', 'Tag 2', 'Tag 3'],
        inputVisible: false,
        inputValue: ''
      };
    },
    methods: {
      handleClose(tag) {
        this.dynamicTags.splice(this.dynamicTags.indexOf(tag), 1);
      },

      showInput() {
        this.inputVisible = true;
        this.$nextTick(_ => {
          this.$refs.saveTagInput.$refs.input.focus();
        });
      },

      handleInputConfirm() {
        let inputValue = this.inputValue;
        if (inputValue) {
          this.dynamicTags.push(inputValue);
        }
        this.inputVisible = false;
        this.inputValue = '';
      }
    }
  }
</script>
```
:::

### Tamaños

Además del tamaño predeterminado, el componente Tag proporciona tres tamaños adicionales para que pueda elegir entre diferentes escenarios.

:::demo Utilice el atributo `size` para establecer tamaños adicionales con `medium`, `small` o `mini`.

```html
<my-tag>Default</my-tag>
<my-tag size="medium">Medium</my-tag>
<my-tag size="small">Small</my-tag>
<my-tag size="mini">Mini</my-tag>
```
:::

### Theme

Tag tiene tres diferentes temas: `dark`、`light` y `plain`

:::demo Use  `effect` para cambiarlo, por defecto es `light`
```html
<div class="tag-group">
  <span class="tag-group__title">Dark</span>
  <my-tag
    v-for="item in items"
    :key="item.label"
    :type="item.type"
    effect="dark">
    {{ item.label }}
  </my-tag>
</div>
<div class="tag-group">
  <span class="tag-group__title">Plain</span>
  <my-tag
    v-for="item in items"
    :key="item.label"
    :type="item.type"
    effect="plain">
    {{ item.label }}
  </my-tag>
</div>

<script>
  export default {
    data() {
      return {
        items: [
          { type: '', label: 'Tag 1' },
          { type: 'success', label: 'Tag 2' },
          { type: 'info', label: 'Tag 3' },
          { type: 'danger', label: 'Tag 4' },
          { type: 'warning', label: 'Tag 5' }
        ]
      }
    }
  }
</script>
```
:::

### Atributos
| Atributo            | Descripción                         | Tipo    | Valores aceptados           | Por defecto |
| ------------------- | ----------------------------------- | ------- | --------------------------- | ----------- |
| type                | tipo de Tag | string  | success/info/warning/danger | —           |
| closable            | si el Tag puede ser removido        | boolean | —                           | false       |
| disable-transitions | si se deshabilitan las animaciones  | boolean | —                           | false       |
| hit                 | si el  Tag tiene un borde resaltado | boolean | —                           | false       |
| color               | color de fondo del Tag              | string  | —                           | —           |
| size                | tamaño del Tag                      | string  | medium / small / mini       | —           |
| effect | Tema del Tag | string | dark / light / plain | light |


### Eventos
| Nombre | Descripción                          | Parametros |
| ------ | ------------------------------------ | ---------- |
| click  | se dispara cuando el Tag es clic     | —          |
| close  | se dispara cuando el Tag es removido | —          |
