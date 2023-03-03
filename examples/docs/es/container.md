## Contenedor
Componentes contenedores para iniciar una estructura básica de un sitio:

`<my-container>`: Contenedor. Cuando este elemento se anida con un `<my-header>` o `<my-footer>`, todos los elementos secundarios se organizan verticalmente.
De lo contrario, de forma horizontal. 

`<my-header>`: Contenedor para cabeceras.

`<my-aside>`: Contenedor para secciones laterales (generalmente, una barra lateral).

`<my-main>`: Contenedor para sección principal.

`<my-footer>`: Contenedor para pie de página.

:::tip
Estos componentes utilizan flex para el diseño, así que asegúrese que el navegador lo soporta. Además, los elementos directos de `<my-container>` tienen que ser uno o más de los últimos cuatro componentes. Y el elemento padre de los últimos cuatro componentes debe ser un `<my-container>`.
:::

### Diseños comunes

:::demo
```html
<my-container>
  <my-header>Cabecera</my-header>
  <my-main>Principal</my-main>
</my-container>

<my-container>
  <my-header>Cabecera</my-header>
  <my-main>Principal</my-main>
  <my-footer>Pie de página</my-footer>
</my-container>

<my-container>
  <my-aside width="200px">Barra lateral</my-aside>
  <my-main>Principal</my-main>
</my-container>

<my-container>
  <my-header>Cabecera</my-header>
  <my-container>
    <my-aside width="200px">Barra lateral</my-aside>
    <my-main>Principal</my-main>
  </my-container>
</my-container>

<my-container>
  <my-header>Cabecera</my-header>
  <my-container>
    <my-aside width="200px">Barra lateral</my-aside>
    <my-container>
      <my-main>Principal</my-main>
      <my-footer>Pie de página</my-footer>
    </my-container>
  </my-container>
</my-container>

<my-container>
  <my-aside width="200px">Barra lateral</my-aside>
  <my-container>
    <my-header>Cabecera</my-header>
    <my-main>Principal</my-main>
  </my-container>
</my-container>

<my-container>
  <my-aside width="200px">Barra lateral</my-aside>
  <my-container>
    <my-header>Cabecera</my-header>
    <my-main>Principal</my-main>
    <my-footer>Pie de página</my-footer>
  </my-container>
</my-container>

<style>
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
```
:::

### Ejemplo

:::demo
```html
<my-container style="height: 500px; border: 1px solid #eee">
  <my-aside width="200px" style="background-color: rgb(238, 241, 246)">
    <my-menu :default-openeds="['1', '3']">
      <my-submenu index="1">
        <template slot="title"><i class="el-icon-message"></i>Navigator One</template>
        <my-menu-item-group>
          <template slot="title">Group 1</template>
          <my-menu-item index="1-1">Option 1</my-menu-item>
          <my-menu-item index="1-2">Option 2</my-menu-item>
        </my-menu-item-group>
        <my-menu-item-group title="Group 2">
          <my-menu-item index="1-3">Option 3</my-menu-item>
        </my-menu-item-group>
        <my-submenu index="1-4">
          <template slot="title">Option4</template>
          <my-menu-item index="1-4-1">Option 4-1</my-menu-item>
        </my-submenu>
      </my-submenu>
      <my-submenu index="2">
        <template slot="title"><i class="el-icon-menu"></i>Navigator Two</template>
        <my-menu-item-group>
          <template slot="title">Group 1</template>
          <my-menu-item index="2-1">Option 1</my-menu-item>
          <my-menu-item index="2-2">Option 2</my-menu-item>
        </my-menu-item-group>
        <my-menu-item-group title="Group 2">
          <my-menu-item index="2-3">Option 3</my-menu-item>
        </my-menu-item-group>
        <my-submenu index="2-4">
          <template slot="title">Option 4</template>
          <my-menu-item index="2-4-1">Option 4-1</my-menu-item>
        </my-submenu>
      </my-submenu>
      <my-submenu index="3">
        <template slot="title"><i class="el-icon-setting"></i>Navigator Three</template>
        <my-menu-item-group>
          <template slot="title">Group 1</template>
          <my-menu-item index="3-1">Option 1</my-menu-item>
          <my-menu-item index="3-2">Option 2</my-menu-item>
        </my-menu-item-group>
        <my-menu-item-group title="Group 2">
          <my-menu-item index="3-3">Option 3</my-menu-item>
        </my-menu-item-group>
        <my-submenu index="3-4">
          <template slot="title">Option 4</template>
          <my-menu-item index="3-4-1">Option 4-1</my-menu-item>
        </my-submenu>
      </my-submenu>
    </my-menu>
  </my-aside>
  
  <my-container>
    <my-header style="text-align: right; font-size: 12px">
      <my-dropdown>
        <i class="el-icon-setting" style="margin-right: 15px"></i>
        <my-dropdown-menu slot="dropdown">
          <my-dropdown-item>View</my-dropdown-item>
          <my-dropdown-item>Add</my-dropdown-item>
          <my-dropdown-item>Delete</my-dropdown-item>
        </my-dropdown-menu>
      </my-dropdown>
      <span>Tom</span>
    </my-header>
    
    <my-main>
      <my-table :data="tableData">
        <my-table-column prop="date" label="Date" width="140">
        </my-table-column>
        <my-table-column prop="name" label="Name" width="120">
        </my-table-column>
        <my-table-column prop="address" label="Address">
        </my-table-column>
      </my-table>
    </my-main>
  </my-container>
</my-container>

<style>
  .el-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }
  
  .el-aside {
    color: #333;
  }
</style>

<script>
  export default {
    data() {
      const item = {
        date: '2016-05-02',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles'
      };
      return {
        tableData: Array(20).fill(item)
      }
    }
  };
</script>
```
:::

### Atributos de contenedor
| Atributo  | Descripción                              | Tipo   | Valores aceptados     | Por defecto                              |
| --------- | ---------------------------------------- | ------ | --------------------- | ---------------------------------------- |
| direction | dirección de diseño para elementos secundarios | string | horizontal / vertical | vertical cuando el elemento está anidado con `el-header`, de lo contrario, horizontal |

### Atributos de cabecera
| Atributo | Descripción           | Tipo   | Valores aceptados | Por defecto |
| -------- | --------------------- | ------ | ----------------- | ----------- |
| height   | altura de la cabecera | string | —                 | 60px        |

### Atributos de barra lateral
| Atributo | Descripción               | Tipo   | Valores aceptados | Por defecto |
| -------- | ------------------------- | ------ | ----------------- | ----------- |
| width    | ancho de la barra lateral | string | —                 | 300px       |

### Atributos de pie de página
| Atributo | Descripción              | Tipo   | Valores aceptados | Por defecto |
| -------- | ------------------------ | ------ | ----------------- | ----------- |
| height   | altura del pie de página | string | —                 | 60px        |