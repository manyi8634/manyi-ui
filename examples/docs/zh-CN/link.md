## Link 文字链接

文字超链接

### 基础用法
基础的文字链接用法。
:::demo
```html
<div>
  <my-link href="https://element.eleme.io" target="_blank">默认链接</my-link>
  <my-link type="primary">主要链接</my-link>
  <my-link type="success">成功链接</my-link>
  <my-link type="warning">警告链接</my-link>
  <my-link type="danger">危险链接</my-link>
  <my-link type="info">信息链接</my-link>
</div>
```
:::

### 禁用状态
文字链接不可用状态。
:::demo
```html
<div>
  <my-link disabled>默认链接</my-link>
  <my-link type="primary" disabled>主要链接</my-link>
  <my-link type="success" disabled>成功链接</my-link>
  <my-link type="warning" disabled>警告链接</my-link>
  <my-link type="danger" disabled>危险链接</my-link>
  <my-link type="info" disabled>信息链接</my-link>
</div>
```
:::

### 下划线
文字链接下划线。
:::demo
```html
<div>
  <my-link :underline="false">无下划线</my-link>
  <my-link>有下划线</my-link>
</div>
```
:::

### 图标

带图标的文字链接可增强辨识度。
:::demo
```html
<div>
  <my-link icon="el-icon-edit">编辑</my-link>
  <my-link>查看<i class="el-icon-view el-icon--right"></i> </my-link>
</div>
```
:::

### Attributes

| 参数           | 说明                           | 类型      | 可选值                               | 默认值  |
| -------------- | ------------------------------ | --------- | ------------------------------------ | ------- |
| type           | 类型                   | string  | primary / success / warning / danger / info | default |
| underline      | 是否下划线                         | boolean | —                                    | true    |
| disabled       | 是否禁用状态                       | boolean | —                                    | false   |
| href           | 原生 href 属性                     | string  | —                                    | -       |
| icon           | 图标类名                       | string  | —                                    | -       |
