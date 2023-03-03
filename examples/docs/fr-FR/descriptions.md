## Descriptions

Display multiple fields in list form.

### Basic usage

:::demo

```html
<my-descriptions title="User Info">
    <my-descriptions-item label="Username">kooriookami</my-descriptions-item>
    <my-descriptions-item label="Telephone">18100000000</my-descriptions-item>
    <my-descriptions-item label="Place">Suzhou</my-descriptions-item>
    <my-descriptions-item label="Remarks">
      <my-tag size="small">School</my-tag>
    </my-descriptions-item>
    <my-descriptions-item label="Address">No.1188, Wuzhong Avenue, Wuzhong District, Suzhou, Jiangsu Province</my-descriptions-item>
</my-descriptions>
```
:::

### Sizes

:::demo

```html
<template>
  <my-radio-group v-model="size">
    <my-radio label="">Default</my-radio>
    <my-radio label="medium">Medium</my-radio>
    <my-radio label="small">Small</my-radio>
    <my-radio label="mini">Mini</my-radio>
  </my-radio-group>

  <my-descriptions class="margin-top" title="With border" :column="3" :size="size" border>
    <template slot="extra">
      <my-button type="primary" size="small">Operation</my-button>
    </template>
    <my-descriptions-item>
      <template slot="label">
        <i class="el-icon-user"></i>
        Username
      </template>
      kooriookami
    </my-descriptions-item>
    <my-descriptions-item>
      <template slot="label">
        <i class="el-icon-mobile-phone"></i>
        Telephone
      </template>
      18100000000
    </my-descriptions-item>
    <my-descriptions-item>
      <template slot="label">
        <i class="el-icon-location-outline"></i>
        Place
      </template>
      Suzhou
    </my-descriptions-item>
    <my-descriptions-item>
      <template slot="label">
        <i class="el-icon-tickets"></i>
        Remarks
      </template>
      <my-tag size="small">School</my-tag>
    </my-descriptions-item>
    <my-descriptions-item>
      <template slot="label">
        <i class="el-icon-office-building"></i>
        Address
      </template>
      No.1188, Wuzhong Avenue, Wuzhong District, Suzhou, Jiangsu Province
    </my-descriptions-item>
  </my-descriptions>

  <my-descriptions class="margin-top" title="Without border" :column="3" :size="size">
    <template slot="extra">
      <my-button type="primary" size="small">Operation</my-button>
    </template>
    <my-descriptions-item label="Username">kooriookami</my-descriptions-item>
    <my-descriptions-item label="Telephone">18100000000</my-descriptions-item>
    <my-descriptions-item label="Place">Suzhou</my-descriptions-item>
    <my-descriptions-item label="Remarks">
      <my-tag size="small">School</my-tag>
    </my-descriptions-item>
    <my-descriptions-item label="Address">No.1188, Wuzhong Avenue, Wuzhong District, Suzhou, Jiangsu Province</my-descriptions-item>
  </my-descriptions>
</template>

<script>
  export default {
    data () {
      return {
        size: ''
      };
    }
  }
</script>
```
:::

### Vertical List

:::demo

```html
<my-descriptions title="Vertical list with border" direction="vertical" :column="4" border>
  <my-descriptions-item label="Username">kooriookami</my-descriptions-item>
  <my-descriptions-item label="Telephone">18100000000</my-descriptions-item>
  <my-descriptions-item label="Place" :span="2">Suzhou</my-descriptions-item>
  <my-descriptions-item label="Remarks">
    <my-tag size="small">School</my-tag>
  </my-descriptions-item>
  <my-descriptions-item label="Address">No.1188, Wuzhong Avenue, Wuzhong District, Suzhou, Jiangsu Province</my-descriptions-item>
</my-descriptions>

<my-descriptions class="margin-top" title="Vertical list without border" :column="4" direction="vertical">
  <my-descriptions-item label="Username">kooriookami</my-descriptions-item>
  <my-descriptions-item label="Telephone">18100000000</my-descriptions-item>
  <my-descriptions-item label="Place" :span="2">Suzhou</my-descriptions-item>
  <my-descriptions-item label="Remarks">
    <my-tag size="small">School</my-tag>
  </my-descriptions-item>
  <my-descriptions-item label="Address">No.1188, Wuzhong Avenue, Wuzhong District, Suzhou, Jiangsu Province</my-descriptions-item>
</my-descriptions>
```
:::

### Customized Style

:::demo

```html
<my-descriptions title="Customized style list" :column="3" border>
  <my-descriptions-item label="Username" label-class-name="my-label" content-class-name="my-content">kooriookami</my-descriptions-item>
  <my-descriptions-item label="Telephone">18100000000</my-descriptions-item>
  <my-descriptions-item label="Place">Suzhou</my-descriptions-item>
  <my-descriptions-item label="Remarks">
    <my-tag size="small">School</my-tag>
  </my-descriptions-item>
  <my-descriptions-item label="Address" :content-style="{'text-align': 'right'}">No.1188, Wuzhong Avenue, Wuzhong District, Suzhou, Jiangsu Province</my-descriptions-item>
</my-descriptions>
<style>
  .my-label {
    background: #E1F3D8;
  }

  .my-content {
    background: #FDE2E2;
  }
</style>
```
:::

### Descriptions Attributes
| Attribute     | Description       | Type       | Accepted Values        | Default   |
|-------------  |---------------- |---------------- |---------------------- |-------- |
| border        | with or without border      | boolean  |          —             |    false     |
| column        | numbers of `Descriptions Item` in one line  | number | — |    3  |
| direction     | direction of list  | string | vertical / horizontal |    horizontal  |
| size          | size of list    | string  |    medium / small / mini  |  — |
| title         | title text, display on the top left    | string  |    —  |  — |
| extra         | extra text, display on the top right    | string  |    —  |  — |
| colon | change default props colon value of Descriptions Item   | boolean |    —  |  true |
| labelClassName          | custom label class name         | string  |          —             |    —     |
| contentClassName          | custom content class name         | string  |          —             |    —     |
| labelStyle          | custom label style | object |          —             |    —     |
| contentStyle         | custom content style | object |          —             |    —     |

### Descriptions Slots

| Name | Description |
|------|--------|
| title | custom title, display on the top left  |
| extra | custom extra area, display on the top right  |

### Descriptions Item Attributes
| Attribute       | Description        | Type       | Accepted Values       | Default   |
|-------------  |---------------- |---------------- |---------------------- |-------- |
| label          | label text         | string  |          —             |    —     |
| span          | colspan of column       | number  |          —             |    1     |
| labelClassName          | custom label class name         | string  |          —             |    —     |
| contentClassName          | custom content class name         | string  |          —             |    —     |
| labelStyle          | custom label style | object |          —             |    —     |
| contentStyle         | custom content style | object |          —             |    —     |

### Descriptions Item Slots

| Name | Description |
|------|--------|
| label | custom label  |
