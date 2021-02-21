# Targets

## Target Sources

```cmake
target_sources(
  foo
  PRIVATE
    foo.h)
```

`target_sources` add non-source files to a targe,t so that they will show up in
IDEs.

- `PUBLIC`, `INTERFACE` will add the target's files to whoever that depends on
  the target
- `PRIVATE` will keep the target's files to itself
- `target_sources` can also add source files, in addition to using
  `add_executable(target, sources)` and `add_library(target, sources)`
