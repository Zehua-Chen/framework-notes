# Shader Attributes

```glsl
attribute vec3 coordinate;

void main(void) {
  gl_Position = vec4(coordinate, 1.0);
}
```

Attributes acts as an input to a shader

- In WebGL2, `in` would save the same purpose
- When an attribute is **disabled**, it uses a default value, and when it is
  **enabled**, it uses a custom value
- Attributes are disabled by default and must be enabled to be used

To assign values to shader attributes

```ts
gl.bindBuffer(gl.ARRAY_BUFFER, data);

// get the index of the attribute from the shader program
const coordinate = gl.getAttribLocation(program, "coordinates");
// describe the type, size ... of the attribute
gl.vertexAttribPointer(coordinate, 3, gl.FLOAT, false, 0, 0);
// tell WebGL to use custom data at gl.ARRAY_BUFFER to the attribute
gl.enableVertexAttribArray(coordinate);
// gl.disableVertexAttribArray(coordinate) would disable the attribute
```
