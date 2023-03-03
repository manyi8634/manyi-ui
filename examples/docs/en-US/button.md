## Button

Commonly used button.

### Basic usage

:::demo Use `type`, `plain`, `round` and `circle` to define Button's style.

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

### Disabled Button

The `disabled` attribute determines if the button is disabled.

:::demo Use `disabled` attribute to determine whether a button is disabled. It accepts a `Boolean` value.

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

### Text Button

Buttons without border and background.

:::demo
```html
<my-button type="text">Text Button</my-button>
<my-button type="text" disabled>Text Button</my-button>
```
:::

### Icon Button

Use icons to add more meaning to Button. You can use icon alone to save some space, or use it with text.

:::demo Use the `icon` attribute to add icon. You can find the icon list in Element icon component. Adding icons to the right side of the text is achievable with an `<i>` tag. Custom icons can be used as well.

```html
<my-button type="primary" icon="el-icon-edit"></my-button>
<my-button type="primary" icon="el-icon-share"></my-button>
<my-button type="primary" icon="el-icon-delete"></my-button>
<my-button type="primary" icon="el-icon-search">Search</my-button>
<my-button type="primary">Upload<i class="el-icon-upload el-icon-right"></i></my-button>
```
:::

### Button Group

Displayed as a button group, can be used to group a series of similar operations.

:::demo Use tag `<my-button-group>` to group your buttons.

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

### Loading Button

Click the button to load data, then the button displays a loading state.

:::demo Set `loading` attribute to `true` to display loading state.

```html
<my-button type="primary" :loading="true">Loading</my-button>
```
:::

### Sizes

Besides default size, Button component provides three additional sizes for you to choose among different scenarios.

:::demo Use attribute `size` to set additional sizes with `medium`, `small` or `mini`.

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

### Attributes
| Attribute      | Description    | Type      | Accepted values       | Default   |
|---------- |-------- |---------- |-------------  |-------- |
| size     | button size   | string  |   medium / small / mini            |    —     |
| type     | button type   | string    |   primary / success / warning / danger / info / text |     —    |
| plain     | determine whether it's a plain button   | boolean    | — | false   |
| round     | determine whether it's a round button   | boolean    | — | false   |
| circle     | determine whether it's a circle button   | boolean    | — | false   |
| loading   | determine whether it's loading   | boolean    | — | false   |
| disabled  | disable the button    | boolean   | —   | false   |
| icon  | icon class name | string   |  —  |  —  |
| autofocus  | same as native button's `autofocus` | boolean   |  —  |  false  |
| native-type | same as native button's `type` | string | button / submit / reset | button |