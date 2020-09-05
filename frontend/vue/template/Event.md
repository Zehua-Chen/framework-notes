# Event

```vue
<template>
  <div>
    <button v-on:click="action"></button>
    <button v-on:click="action(value)"></button>
    <button v-on:click="action(value, ...arguments)"></button>
    <button v-on:click="action(value, $event)"></button>
    <button v-on:click="(param) => action(value, param)"></button>
  </div>
</template>
```

`v-on:event="action"` would invoke an action upon an event

- `$event` refers to the parameter emitted by the event (if it only exists one)
  - Primarily used for HTML events

# Short Hand

```vue
<template>
  <div>
    <button @click="action"></button>
    <button @[event]="action(params)"></button>
  </div>
</template>
```
