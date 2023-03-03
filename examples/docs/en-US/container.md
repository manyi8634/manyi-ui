## Container
Container components for scaffolding basic structure of the page:

`<my-container>`: wrapper container. When nested with a `<my-header>` or `<my-footer>`, all its child elements will be vertically arranged. Otherwise horizontally.

`<my-header>`: container for headers.

`<my-aside>`: container for side sections (usually a side nav).

`<my-main>`: container for main sections.

`<my-footer>`: container for footers.

:::tip
These components use flex for layout, so please make sure your browser supports it. Besides, `<my-container>`'s direct child elements have to be one or more of the latter four components. And father element of the latter four components must be a `<my-container>`.
:::

### Common layouts

:::demo
```html
<my-container>
  <my-header>Header</my-header>
  <my-main>Main</my-main>
</my-container>

<my-container>
  <my-header>Header</my-header>
  <my-main>Main</my-main>
  <my-footer>Footer</my-footer>
</my-container>

<my-container>
  <my-aside width="200px">Aside</my-aside>
  <my-main>Main</my-main>
</my-container>

<my-container>
  <my-header>Header</my-header>
  <my-container>
    <my-aside width="200px">Aside</my-aside>
    <my-main>Main</my-main>
  </my-container>
</my-container>

<my-container>
  <my-header>Header</my-header>
  <my-container>
    <my-aside width="200px">Aside</my-aside>
    <my-container>
      <my-main>Main</my-main>
      <my-footer>Footer</my-footer>
    </my-container>
  </my-container>
</my-container>

<my-container>
  <my-aside width="200px">Aside</my-aside>
  <my-container>
    <my-header>Header</my-header>
    <my-main>Main</my-main>
  </my-container>
</my-container>

<my-container>
  <my-aside width="200px">Aside</my-aside>
  <my-container>
    <my-header>Header</my-header>
    <my-main>Main</my-main>
    <my-footer>Footer</my-footer>
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

### Example

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

### Container Attributes
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| direction | layout direction for child elements | string | horizontal / vertical | vertical when nested with `el-header` or `el-footer`; horizontal otherwise |

### Header Attributes
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| height | height of the header | string | — | 60px |

### Aside Attributes
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| width | width of the side section | string | — | 300px |

### Footer Attributes
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| height | height of the footer | string | — | 60px |