# WebGL

1. Obtaining context
2. Create shader, vertex data
3. Configure Rendering
4. Rendering

## Obtaining GL Context

All WebGL operations requires some kind of context to run. GL Context can be
obtained from `<canvas>` elements

```ts
let canvas = document.getElementById("canvas");

if (!canvas) {
  alert("canvas is not found");
  throw new Error("canvas is not found");
}

if (!(canvas instanceof HTMLCanvasElement)) {
  throw new Error("canvas is not of HTMLCanvasElement");
}

const gl = canvas.getContext("webgl");
```

## Configure Rendering

### Depth Test

Depth test is hidden surface removal; can be toggled using

```ts
gl.enable(gl.DEPTH_TEST);
gl.disable(gl.DEPTH_TEST);
```

Keep in mind that `z=-1` will cover `z=1`

Before rendering begin, reset depth buffer

```ts
gl.clear(gl.DEPTH_BUFFER_BIT);
```

### Background Color

Background color (aka. clear color) can be configured using; **note that this
does not set background color**

```ts
// set a color preset
gl.clearColor(...);
```

Before rendering begin, colors are cleared using

```ts
// revert to color preset
// this actually set the background color
gl.clear(gl.COLOR_BUFFER_BIT);
```

### Viewport

Where in the `<canvas />` to draw

```ts
gl.viewport(x, y, width, height);
```

## Rendering

```ts
gl.bindBuffer(gl.ARRAY_BUFFER, vertices);
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, indices);
gl.drawElements(gl.TRIANGLES, 3, gl.UNSIGNED_SHORT, 0);
```

`gl.drawElements` issues the draw call

- Vertex data are taken from `gl.ARRAY_DATA`
- Indices data are taken from `gl.ELEMENT_ARRAY_BUFFER`

### Clip Space

- `x`: `[-1, 1]`
- `y`: `[-1, 1]`
- `z`: `[-1, 1]`
  - `-1` is the closest to the user
