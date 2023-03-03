## Link

Texto con hipervínculo

### Básico

Texto con hipervínculo básico
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

### Deshabilitar

Deshabilita el hipervínculo
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

### Subrayado

Subrayado del hipervínculo
:::demo

```html
<div>
  <my-link :underline="false">Without Underline</my-link>
  <my-link>With Underline</my-link>
</div>
```

:::

### Icono

Hipervínculo con icono
:::demo

```html
<div>
  <my-link icon="el-icon-edit">Edit</my-link>
  <my-link>Check<i class="el-icon-view el-icon--right"></i> </my-link>
</div>
```

:::

### Atributos

| Atributo  | Descripción                                          | Tipo    | Opciones                                    | Por defecto |
| --------- | ---------------------------------------------------- | ------- | ------------------------------------------- | ----------- |
| type      | tipo                                                 | string  | primary / success / warning / danger / info | default     |
| underline | si el hipervínculo estará subrayado                  | boolean | —                                           | true        |
| disabled  | si el componente esta deshabilitado                  | boolean | —                                           | false       |
| href      | lo mismo que el valor nativo del hipervínculo `href` | string  | —                                           | -           |
| icon      | nombre de clase del icono                            | string  | —                                           | -           |
