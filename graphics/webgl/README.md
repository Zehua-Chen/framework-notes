# WebGL

1. Obtaining context
2. Create shader, vertex data
3. Configure Rendering
4. Rendering
5. Request next frame

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

Depth test performs hidden surface removal; can be toggled using

```ts
gl.enable(gl.DEPTH_TEST);
gl.disable(gl.DEPTH_TEST);
```

Before rendering begin, reset depth buffer

```ts
gl.clear(gl.DEPTH_BUFFER_BIT);
```

- Depth buffer default value can be set using
  ```ts
  gl.clearDepth(depth);
  ```
  Default value is `1`
- Depth function can be configured using
  ```ts
  gl.depthFunc(func);
  ```
  Default value is `gl.LESS`. This means that with default values, vertices with
  `z=1` would not be drawn

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
gl.bindBuffer(gl.ELEMENT_ARRAY_BUFFER, indices);
gl.drawElements(gl.TRIANGLES, 3, gl.UNSIGNED_SHORT, 0);
```

`gl.drawElements` issues the draw call

- Vertex data should be passed using shaders
- Indices data are taken from `gl.ELEMENT_ARRAY_BUFFER`. WebGL would use the
  indices and the vertices processed by the shader program to form shapes

## Request Next Frame

```ts
requestAnimationFrame(draw);
```

Request animtion frame registers a callback to the browser. The callback would
be used produce the next frame

The callback would be call with a number as a parameter that represent **the
current timestamp in milliseconds**

# Resources

- [WebGL Fundamentals](https://webglfundamentals.org/webgl/lessons/webgl-indexed-vertices.html)
