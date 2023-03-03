## Divider

The dividing line that separates the content.

### Basic usage

Divide the text of different paragraphs.

:::demo
```html
<template>
  <div>
    <span>I sit at my window this morning where the world like a passer-by stops for a moment, nods to me and goes.</span>
    <my-divider></my-divider>
    <span>There little thoughts are the rustle of leaves; they have their whisper of joy in my mind.</span>
  </div>
</template>
```
:::

### Custom content

You can customize the content on the divider line.


:::demo
```html
<template>
  <div>
    <span>What you are you do not see, what you see is your shadow. </span>
    <my-divider content-position="left">Rabindranath Tagore</my-divider>
    <span>I cannot choose the best. The best chooses me.</span>
    <my-divider><i class="el-icon-star-on"></i></my-divider>
    <span>My wishes are fools, they shout across thy song, my Master. Let me but listen.</span>
    <my-divider content-position="right">Rabindranath Tagore</my-divider>
  </div>
</template>
```
:::

### Vertical divider

:::demo
```html
<template>
  <div>
    <span>Rain</span>
    <my-divider direction="vertical"></my-divider>
    <span>Home</span>
    <my-divider direction="vertical"></my-divider>
    <span>Grass</span>
  </div>
</template>
```
:::

### Divider Attributes
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|-------------  |---------------- |---------------- |---------------------- |-------- |
| direction      | Set divider's direction  | string  |          horizontal / vertical           |    horizontal     |
| content-position      | customize the content on the divider line | String  |  left / right / center  |  center |