# Special Props

- `key` and `ref` props are internally used by react and not passed to
  components
  - To access `ref`, use `React.forwardRef((props, ref) => Component)`
