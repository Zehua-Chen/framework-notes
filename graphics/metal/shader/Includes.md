# Includes

```c++
#ifndef __METAL_VERSION__
// Put content that is not allowed in Metal shader here
#endif
```

Metal compiler would define `__METAL_VERSION__` automatically.

- If the macro is not defined, then compilation unit the header is currently in
  is not a Metal shader file
