# Event

```vue
<template>
  <div>
    <button v-on:click="action"></button>
    <button v-on:click="action(params)"></button>
  </div>
</template>
```

`v-on:event="action"` would invoke an action upon an event

- Can pass parameters

## Short Hand

```vue
<template>
  <div>
    <button @click="action"></button>
    <button @[event]="action(params)"></button>
  </div>
</template>
```
