# Creating Shaders

```ts
let shader = gl.createShader();
gl.shaderSource(shader, "");
gl.compile(shader);
```

## Shader Program

Shaders must be included in shader programs to be used

```ts
let program = gl.createProgram();
gl.attachShader(vertexShader);
gl.attachShader(fragmentShader);

gl.linkProgram(program);
```

- Shader must be compiled before being attached

Shader programs can then be used by webgl

```ts
gl.useProgram(program);
```
