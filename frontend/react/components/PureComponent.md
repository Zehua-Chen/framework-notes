# Pure Component

- A pure component is a component whose `shouldComponentUpdate()` method shallow
  compares the new state and the new props object with the old state and the old
  props;
  - Props are passed as objects;

## Shallow Equal

- Two primitives are said to be shallow equal if `===` returns `true`;
- Two complex objects are said to be shallow equal if all their keys are equal
  when the keys are compared using the `===` operator;
- Source: `react/packages/shared/shallowEqual.js`;

# Memo

`React.memo` is a higher order component used to make function components only
update when the new props object is no longer shallow equal to the old prop;
