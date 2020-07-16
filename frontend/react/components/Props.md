# Special Props

- `key` and `ref` props are internally used by react and not passed to
  components

  - To access `ref`, use `React.forwardRef((props, ref) => /* Use ref here */)`

    ```jsx
    class Foo extends Component {
      render() {
        const { forwardedRef } = this.props;

        return <div ref={forwardedRef}></div>;
      }
    }

    export default React.forwardRef((props, ref) => (
      <Foo {...props} forwardedRef={ref} />
    ));
    ```

    Since the function only takes functional components, class components needs
    to be wrapped.
