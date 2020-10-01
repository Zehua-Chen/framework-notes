# `drawElements`

```ts
declare class WebGLRenderingContext {
  drawElements(mode: number, count: number, type: number, offset: number): void;
}
```

## Paramaeters

- `mode`: what to draw
  - `gl.TRIANGLES`
- `count`: how many elements to be drawn
  - When using `gl.TRIANGLES` as mode, elements refer to vertices
  - Size of each vertex is up dependent on `mode`
- `type`: type of elements in element array buffer
  - `gl.UNSIGNED_BYTE`: 1 byte
  - `gl.UNSIGNED_SHORT`: 2 byte
