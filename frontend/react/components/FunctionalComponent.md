# Functional Components

Due to the stateless nature of functional components, hooks (which preserve
states) should always be prefered

- **ref**: `React.useRef(initial)`

# Default Props

```ts
interface SliderProps {}

function SliderProps(props: SliderProps) {
  return ...
}

declare namespace Slider {
  export var defaultProps: SliderProps;
}

SliderProps.defaultProps = {};
```

- Default props are assigned by using `Component.defaultProps` (as in class
  components)
- To apply types to default props, use an ambient typescript namespace
  - Preprocessors like babel cannot handle real namespaces without additional
    configuration
  - Some toolchains does not allow customizing babel (ex. react-scripts)
