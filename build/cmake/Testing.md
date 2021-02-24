# Testing

To enable testing for "this" dictory and all directory below

```cmake
enable_testing()
```

To add a test

```cmake
add_executable(test test.cc)
add_test(NAME test COMMAND test)
```

To run the test

```
ninja test
```

## Google Test

- `gtest_add_tests` scan source codes for tests
  - **Trigger cmake regenerate every time file changes**
- `gtest_discover_tests` query compiled executable for tests
  - **Does not trigger cmake regenerate every time file changes**
