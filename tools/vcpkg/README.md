# Consumer

```json
{
  "name": "cs419",
  "version-string": "0.1.0",
  "dependencies": ["pngpp"]
}
```

- `name` and `version-string` are required properties

## CMake

1. Running `cmake <path> -G Ninja -DCMAKE_TOOLCHAIN_FILE=...` will create a
   `vcpkg_installed` directory where the dependencies are installed.
2. Packages can then be used via `find_package` or `find_path` commands
