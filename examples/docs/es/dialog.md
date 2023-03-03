## Dialog

Informar a usuarios preservando el estado de la página actual.

### Uso Básico

Dialog abre una caja de diálogo, y es bastante personalizable.

:::demo Establezca el atributo `visible` con un booleano, y el Dialog se muestra cuando es `true`. El diálogo tiene dos partes: `body` y `footer`,  este último requiere un slot llamado `footer`. El atributo `title` es opcional (vacío por defecto) y sirve para definir un título. Por último, este ejemplo muestra cómo se utiliza `before-close`.


```html
<my-button type="text" @click="dialogVisible = true">click to open the Dialog</my-button>

<my-dialog
  title="Tips"
  :visible.sync="dialogVisible"
  width="30%"
  :before-close="handleClose">
  <span>This is a message</span>
  <span slot="footer" class="dialog-footer">
    <my-button @click="dialogVisible = false">Cancel</my-button>
    <my-button type="primary" @click="dialogVisible = false">Confirm</my-button>
  </span>
</my-dialog>

<script>
  export default {
    data() {
      return {
        dialogVisible: false
      };
    },
    methods: {
      handleClose(done) {
        this.$confirm('Are you sure to close this dialog?')
          .then(_ => {
            done();
          })
          .catch(_ => {});
      }
    }
  };
</script>
```
:::

:::tip

`before-close`  sólo funciona cuando el usuario hace clic en el icono de cerrar o en el fondo. Si tiene botones que cierran el cuadro de diálogo en el slot llamado `footer`, puede agregar lo que haría `before-close` en el manejador de eventos de los botones.

:::

### Personalizaciones


El contenido del Diálogo puede ser cualquier cosa, incluso una tabla o un formulario. Este ejemplo muestra cómo usar Element Table y Form con Dialog

:::demo

```html
<!-- Table -->
<my-button type="text" @click="dialogTableVisible = true">open a Table nested Dialog</my-button>

<my-dialog title="Shipping address" :visible.sync="dialogTableVisible">
  <my-table :data="gridData">
    <my-table-column property="date" label="Date" width="150"></my-table-column>
    <my-table-column property="name" label="Name" width="200"></my-table-column>
    <my-table-column property="address" label="Address"></my-table-column>
  </my-table>
</my-dialog>

<!-- Form -->
<my-button type="text" @click="dialogFormVisible = true">open a Form nested Dialog</my-button>

<my-dialog title="Shipping address" :visible.sync="dialogFormVisible">
  <my-form :model="form">
    <my-form-item label="Promotion name" :label-width="formLabelWidth">
      <my-input v-model="form.name" autocomplete="off"></my-input>
    </my-form-item>
    <my-form-item label="Zones" :label-width="formLabelWidth">
      <my-select v-model="form.region" placeholder="Please select a zone">
        <my-option label="Zone No.1" value="shanghai"></my-option>
        <my-option label="Zone No.2" value="beijing"></my-option>
      </my-select>
    </my-form-item>
  </my-form>
  <span slot="footer" class="dialog-footer">
    <my-button @click="dialogFormVisible = false">Cancel</my-button>
    <my-button type="primary" @click="dialogFormVisible = false">Confirm</my-button>
  </span>
</my-dialog>

<script>
  export default {
    data() {
      return {
        gridData: [{
          date: '2016-05-02',
          name: 'John Smith',
          address: 'No.1518,  Jinshajiang Road, Putuo District'
        }, {
          date: '2016-05-04',
          name: 'John Smith',
          address: 'No.1518,  Jinshajiang Road, Putuo District'
        }, {
          date: '2016-05-01',
          name: 'John Smith',
          address: 'No.1518,  Jinshajiang Road, Putuo District'
        }, {
          date: '2016-05-03',
          name: 'John Smith',
          address: 'No.1518,  Jinshajiang Road, Putuo District'
        }],
        dialogTableVisible: false,
        dialogFormVisible: false,
        form: {
          name: '',
          region: '',
          date1: '',
          date2: '',
          delivery: false,
          type: [],
          resource: '',
          desc: ''
        },
        formLabelWidth: '120px'
      };
    }
  };
</script>
```
:::

### Diálogo anidado
Si un diálogo está anidado en otro diálogo, se requiere append-to-body.

:::demo Normalmente no recomendamos el uso de Dialog anidado. Si necesita que se muestren múltiples diálogos en la página, puede simplemente aplanarlos para que sean hermanos entre sí. Si debe anidar un Diálogo dentro de otro Diálogo, establezca `append-to-body` del Diálogo anidado como true, y lo añadirá al cuerpo en lugar de su nodo padre, para que ambos Diálogos puedan ser correctamente renderizados.

```html
<template>
  <my-button type="text" @click="outerVisible = true">open the outer Dialog</my-button>
  
  <my-dialog title="Outer Dialog" :visible.sync="outerVisible">
    <my-dialog
        width="30%"
        title="Inner Dialog"
        :visible.sync="innerVisible"
        append-to-body>
    </my-dialog>
    <div slot="footer" class="dialog-footer">
      <my-button @click="outerVisible = false">Cancel</my-button>
      <my-button type="primary" @click="innerVisible = true">open the inner Dialog</my-button>
    </div>
  </my-dialog>
</template>

<script>
  export default {
    data() {
      return {
        outerVisible: false,
        innerVisible: false
      };
    }
  }
</script>
```
:::

### Contenido centrado
El contenido de Diálogo se puede centrar.

:::demo Ajuste `center` en `true` para centrar el encabezado y el pie de página del cuadro de diálogo horizontalmente. `center` sólo afecta al encabezado y pie de página de Dialog. El cuerpo de Dialog puede ser cualquier cosa, así que a veces no se ve bien cuando está centrado. Necesitas escribir algún CSS si deseas centrar el cuerpo también.

```html
<my-button type="text" @click="centerDialogVisible = true">Click to open the Dialog</my-button>

<my-dialog
  title="Warning"
  :visible.sync="centerDialogVisible"
  width="30%"
  center>
  <span>It should be noted that the content will not be aligned in center by default</span>
  <span slot="footer" class="dialog-footer">
    <my-button @click="centerDialogVisible = false">Cancel</my-button>
    <my-button type="primary" @click="centerDialogVisible = false">Confirm</my-button>
  </span>
</my-dialog>

<script>
  export default {
    data() {
      return {
        centerDialogVisible: false
      };
    }
  };
</script>
```
:::

:::tip
El contenido de Dialog se renderiza en modo lazy, lo que significa que la ranura por defecto no se renderiza en el DOM hasta que se abre por primera vez. Por lo tanto, si necesita realizar una manipulación DOM o acceder a un componente mediante ref, hágalo en el callback del evento `open`.
:::

:::tip

Si la variable ligada a `visible` se gestiona en el Vuex store, el `.sync` no puede funcionar correctamente. En este caso, elimine el modificador `.sync`, escuche los eventos de `open` y `close` Dialog, y confirme las mutaciones Vuex para actualizar el valor de esa variable en los manejadores de eventos.

:::

### Atributo

| Atributo              | Descripción                              | Tipo                                     | Valores aceptados | Por defecto |
| --------------------- | ---------------------------------------- | ---------------------------------------- | ----------------- | ----------- |
| visible               | visibilidad del Diálogo, apoya el modificador .sync | boolean                                  | —                 | false       |
| title                 | título de Diálogo. También se puede pasar con un slot con nombre (ver la tabla siguiente) | string                                   | —                 | —           |
| width                 | anchura de Diálogo                       | string                                   | —                 | 50%         |
| fullscreen            | si el diálogo ocupa pantalla completa    | boolean                                  | —                 | false       |
| top                   | valor de `margin-top` del Diálogo CSS    | string                                   | —                 | 15vh        |
| modal                 | si se muestra una máscara                | boolean                                  | —                 | true        |
| modal-append-to-body  | si adjuntar modal al elemento de cuerpo. Si es falso,el modal se agregará al elemento principal de Diálogo | boolean                                  | —                 | true        |
| append-to-body        | Si adjuntar el cuadro de diálogo al cuerpo | boolean                                  | —                 | false       |
| lock-scroll           | Si el scroll del cuerpo está desactivado mientras se muestra el cuadro de diálogo | boolean                                  | —                 | true        |
| custom-class          | nombres de clase personalizada para el Diálogo | string                                   | —                 | —           |
| close-on-click-modal  | si el Diálogo puede ser cerrado haciendo clic en la máscara | boolean                                  | —                 | true        |
| close-on-press-escape | si el Diálogo puede ser cerrado presionando ESC | boolean                                  | —                 | true        |
| show-close            | si mostrar un botón de cerrar            | boolean                                  | —                 | true        |
| before-close          | una devolución de llamada antes de que se cierre el cuadro de diálogo, y evitar cerrar el cuadro de diálogo | función(done) `done`se usa para cerrar el diálog | —                 | —           |
| center                | si alinear el encabezado y el pie de página en el centro | boolean                                  | —                 | false       |
| destroy-on-close      | Destruir elementos en Dialog cuando se cierra | boolean                                  | —                 | false         |

### Slots

| Nombre | Descripción                            |
| ------ | -------------------------------------- |
| —      | contenido de Diálogo                   |
| title  | contenido del título de Diálogo        |
| footer | contenido del pie de página de Diálogo |

### Eventos
| Nombre de Evento | Descripción                   | Parámetros |
| ---------------- | ---------------------------------------- | ---------- |
| open             | se activa cuando se abre el cuadro de Diálogo | —          |
| opened           | se activa cuando la animación de apertura del Dialog termina. | — |
| close            | se dispara cuando el Diálogo se cierra   | —          |
| closed           | se activa cuando finaliza la animación de cierre del Diálog | — |

