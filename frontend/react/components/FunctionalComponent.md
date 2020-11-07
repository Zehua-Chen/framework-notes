# Hooks

Some hooks with functions as parameters, like `useEffect(fn, dependencies)` take
a list of values as its dependencies and would only rerun the function when the
dependencies has changed. **Passing an empty list would cause the function to be
only run once**

```ts
function Foo(): JSX.Element {
  useEffect(() => {
    // componentDidMount
  }, []);
  return <div></div>;
}
```

## Refs

- **ref**: `React.useRef(initial)`

## Memoization

## `useCallback`

`useCallback` uses `useMemo` to build a memoized callback; useful for

- Event handlers
- Avoid unecsssary renders in memoized children components

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
