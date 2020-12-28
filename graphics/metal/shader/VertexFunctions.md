# Overview

```cpp
[[vertex]] vertex_output vertex_func() {
  return vertex_output{};
}
```

Vertex functions are used to process vertices before **rasterization**

- Vertex functions must be marked with `[[vertex]]`

# Return Type

Output of vertex functions has to be one of the following

- `void`, only if rasterization is disabled
- `float4`
- A custom type that has one field of type `float4` marked using the `position`
  attribute;
  ```cpp
  struct vertex_output {
    float4 position [[position]];
  };
  ```
