## Result

Used to give feedback on the result of user's operation or access exception.

### Basic usage

:::demo

```html
<my-row>
  <my-col :sm="12" :lg="6">
    <my-result icon="success" title="Success Tip" subTitle="Please follow the instructions">
      <template slot="extra">
        <my-button type="primary" size="medium">Back</my-button>
      </template>
    </my-result>
  </my-col>
  <my-col :sm="12" :lg="6">
    <my-result icon="warning" title="Warning Tip" subTitle="Please follow the instructions">
      <template slot="extra">
        <my-button type="primary" size="medium">Back</my-button>
      </template>
    </my-result>
  </my-col>
  <my-col :sm="12" :lg="6">
    <my-result icon="error" title="Error Tip" subTitle="Please follow the instructions">
      <template slot="extra">
        <my-button type="primary" size="medium">Back</my-button>
      </template>
    </my-result>
  </my-col>
  <my-col :sm="12" :lg="6">
    <my-result icon="info" title="Info Tip" subTitle="Please follow the instructions">
      <template slot="extra">
        <my-button type="primary" size="medium">Back</my-button>
      </template>
    </my-result>
  </my-col>
</my-row>
```

:::

### Customized content

:::demo

```html
<my-result title="404" subTitle="Sorry, request error">
  <template slot="icon">
    <my-image src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png"></my-image>
  </template>
  <template slot="extra">
    <my-button type="primary" size="medium">Back</my-button>
  </template>
</my-result>
```

:::

### Result Attributes

| Attribute     | Description    | Type            | Accepted Values      | Default   |
|-------------  |---------------- |---------------- |---------------------- |-------- |
| title          | title         | string  |          —             |    —     |
| sub-title    | sub title  | string | — |    —  |
| icon  | icon type    | string  |    success / warning / info / error  |  info |

### Result Slots

| Name | Description |
|------|--------|
| icon | custom icon  |
| title | custom title     |
| subTitle | custom sub title     |
| extra | custom  extra area    |
