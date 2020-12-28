# Overview

```cpp
[[fragment]]
float4 fragment_func(vertex_output output [[stage_in]]) {

}
```

# Parameters

- **Vertex Output**: vertex output can be retrieved using
  `vertex_output output [[stage_in]]`

# Return

Must return a `float4` with each component in range `[0, 1]`
