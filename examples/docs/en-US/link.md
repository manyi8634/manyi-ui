## Link

Text hyperlink

### Basic

Basic text link
:::demo

```html
<div>
  <my-link href="https://element.eleme.io" target="_blank">default</my-link>
  <my-link type="primary">primary</my-link>
  <my-link type="success">success</my-link>
  <my-link type="warning">warning</my-link>
  <my-link type="danger">danger</my-link>
  <my-link type="info">info</my-link>
</div>
```

:::

### Disabled

Disabled state of link
:::demo

```html
<div>
  <my-link disabled>default</my-link>
  <my-link type="primary" disabled>primary</my-link>
  <my-link type="success" disabled>success</my-link>
  <my-link type="warning" disabled>warning</my-link>
  <my-link type="danger" disabled>danger</my-link>
  <my-link type="info" disabled>info</my-link>
</div>
```

:::

### Underline

Underline of link
:::demo

```html
<div>
  <my-link :underline="false">Without Underline</my-link>
  <my-link>With Underline</my-link>
</div>
```

:::

### Icon

Link with icon
:::demo

```html
<div>
  <my-link icon="el-icon-edit">Edit</my-link>
  <my-link>Check<i class="el-icon-view el-icon--right"></i> </my-link>
</div>
```

:::

### Attributes

| Attribute | Description                         | Type    | Options                                     | Default |
| --------- | ----------------------------------- | ------- | ------------------------------------------- | ------- |
| type      | type                                | string  | primary / success / warning / danger / info | default |
| underline | whether the component has underline | boolean | —                                           | true    |
| disabled  | whether the component is disabled   | boolean | —                                           | false   |
| href      | same as native hyperlink's `href`   | string  | —                                           | -       |
| icon      | class name of icon                  | string  | —                                           | -       |
