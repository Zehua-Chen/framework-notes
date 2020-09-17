# State

## General

- `setState` will make a "request" for state to be updated
  - Depending on where `setState` is called, different priorities will be
    assgined (ex. updates in events will have a higher priority than those from
    network requests)
  - **Request with higher priorities are more likely to be run sync; others are
    more likely to be async**
  - React **may batch several enqueued changes** and then apply them together;
- The component is always re-rendered unless "shouldComponentUpdate()" returns
  false;
- `setState` can take a completion callback
- After a component's real DOM is updated, both `componentDidUpdate()` and the
  completion callback will be called; it is recommended to reference the new
  state in `componentDidUpdate()`;

## Variants

`setState(updater, callback)`

- `updater: (state, props) => changes` will be called with the updated state
  from the previous executed request and props passed in and returns changes to
  the current state;
  - `changes: any` should be the changes to the current state;
    - The changes will be shallow merged into the current state;
- `callback`: called after DOM update has occured
  - **Note that schedule updates in callback would prevent update batching**;

`setState(update, callabck)`

This form is discouraged due to the async nature of update
