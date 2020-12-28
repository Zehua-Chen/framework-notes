# Metal Shading Language

- Based on C++14 syntax
  - No C++ STL allowed

## Macros

- `__METAL_VERSION__`: set to the version of Metal shading language
- `__METAL_MACOS__`: set if compiled for mac
- `__METAL_IOS__`: set if compiled for iOS

## Attributes

```cpp
void foo(constant buffer *buffer [[buffer(BUFFER_INDEX)]]) {
}
```

- `[[stage_in]]`: vertex or fragment shader argument
  - **Fragment shader**: mark the output of vertex shader
- `[[vertex_id]]`: ushort or uint to indicate the vertex index.
- `[[buffer(index)]]`: it specifies the buffer locations for the function
  arguments. A vertex function can read per-vertex inputs by indexing into a
  buffer(s) passed as arguments to the vertex function using the vertex and
  instance IDs.
- `[[texture(index)]]`: Textures (including texture buffers).
- `[[sampler(index)]]`: Samples that define how to access texture data.
- `[[threadpositionin_grid]]`: The position of the thread in the grid.

## Address Space

```cpp
void foo(constant buffer *buffer) {
}
```

### Graphics Function

- `device`: read / write
- `constant`: read-only

### Compute Function

- `threadgroup`: The entire thread in the thread group is shared.
- `thread`: Can’t be referenced from other threads.

# Building

## Command Line

```
xcrun -sdk macosx metal -c MyLibrary.metal -o MyLibrary.air
xcrun -sdk macosx metallib MyLibrary.air -o MyLibrary.metallib
```

- `metal`: compiles `.metal` files into `.air` files (intermediate
  representation of Metal shaders)
- `metal-ar`: archives several `.air` files into an `.metalar` file
- `metallib`: build `.air`, `.metalar` files into a `.metallib` file (Metal
  Library loaded at runtime)

[Source](https://developer.apple.com/documentation/metal/libraries/building_a_library_with_metal_s_command-line_tools)
