# Overview

`FetchContent` downloads content at generation time, `ExternalProject` downloads
content at build time

# `FetchContent`

```cmake
include(FetchContent)

FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG release-1.10.0)

FetchContent_GetProperties(googletest)

if(NOT googletest_POPULATED)
  # get google test if goole test not added
  FetchContent_Populate(googletest)

  add_subdirectory(${googletest_SOURCE_DIR} ${googletest_BINARY_DIR})
endif()
```
