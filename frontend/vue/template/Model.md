# Model

`v-model` creates a two-way data binding

```vue
<template>
  <custom-component v-model="property"></custom-component>
</template>
```

On most elements, `v-model` uses the prop `value` and the event `input` to
establish the two-way data binding. **However, vue template compiler would use
the appropriate prop and event on special cases**

# Custom Props and Events

```ts
import Vue from "vue";

export default Vue.extend({
  model: {
    prop: "",
    event: "",
  },
});
```

Use custom prop to receive data and custom event to update data
