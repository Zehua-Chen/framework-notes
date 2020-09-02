# GLSL

GLSL is the language used to write shaders for WebGL

## Precision

```glsl
#ifdef GL_FRAGMENT_PRECISION_HIGH
precision highp float;
#else
precision mediump float;
#endif
```

Precisions are qualified using `precision qualifier type`

- `highp`: high precision floating points
  - Available when `GL_FRAGMENT_PRECISION_HIGH` is defined
- `mediump`: medium precision floating points
- `lowp`: low precision floating points

Vertex shader has default precision, fragment shader does not

## `uniform` (Uniform Qualified Variable)

```glsl
uniform mat4 transformation;

void main(void) {
  // ...
}
```

It can be initialized by the application and passed to the fragment shader or
the vertex shader.

- Remains the same across invocation of the shader program

## `varying`

```glsl
varying vec4 v_color;

void main(void) {
  // ...
}
```

Shared variable across vertex and fragment shader
