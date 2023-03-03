## Badge

A number or status mark on buttons and icons.

### Basic usage

Displays the amount of new messages.

:::demo The amount is defined with `value` which accepts `Number` or `String`.

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

### Max value

You can customize the max value.

:::demo The max value is defined by property `max` which is a `Number`. Note that it only works when `value` is also a `Number`.

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

### Customizations

Displays text content other than numbers.

:::demo When `value` is a `String`, it can display customized text.

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

### Little red dot

Use a red dot to mark content that needs to be noticed.

:::demo Use the attribute `is-dot`. It is a `Boolean`.

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

### Attributes
| Attribute     | Description     | Type            | Accepted Values       | Default |
|-------------  |---------------- |---------------- |---------------------- |-------- |
| value         | display value   | string, number  |          —            |    —    |
| max           |  maximum value, shows '{max}+' when exceeded. Only works if `value` is a `Number`   | number  |         —              |     —    |
| is-dot        | if a little dot is displayed | boolean   |    —           |  false  |
| hidden        | hidden badge    | boolean         |          —            |  false  |
| type          | button type     | string          | primary / success / warning / danger / info |   —  |
