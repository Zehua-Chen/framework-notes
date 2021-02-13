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
