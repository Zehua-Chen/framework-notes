# Set States

`setState(..., callabck)`

- `setState(..., callback)` will enqueue changes to the current state and then
  trigger re-render when the changes are effective
  - React does not always immediately apply the state changes and then re-render
    for perceived user experience;
  - React may batch several enqueued changes and then apply them together;
- The component is always re-rendered unless "shouldComponentUpdate()" returns
  false;
- After a component is re-rendered, both `componentDidUpdate()` and `callback`
  will be called; it is recommended to reference the new state in
  `componentDidUpdate()`;

`setState(updater, callback)`

- `updater: (state, props) => changes` will be called with the current state and
  props passed in and returns changes to the current state;
  - The changes will be shallow merged into the current state;
    `setState(changes, callback)`
- `changes: any` should be the changes to the current state;
  - The changes will be shallow merged into the current state;
