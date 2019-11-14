# Life Cycle

## Mounting

1. `constructor(props: any)`
2. `static getDerivedStateFromProps(props, state)`
3. `render()`
4. `componentDidMount()`

## Updating

1. `static getDerivedStateFromProps()`
2. `shouldComponentUpdate()`
3. `render()`
4. `getSnapshotBeforeUpdate()`
5. `componentDidUpdate()`

## Unmount

1. `componentWillUnmount()`

## Error Handnling

1. `static getDerivedStateFromError()`
2. `componentDidCatch()`
