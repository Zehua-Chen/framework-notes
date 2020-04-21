# Subprojects

Subprojects must be included in the `settings.gradle` file

```gradle
include 'console', `other`
```

In case the subproject lives in a deeper level

```gradle
include ":project"
project(":project").projectDir = new File("xxx");
```

## Root Level Configurations

In the root `build.gradle`

- Shared configurations can be configured
- Additional configurations can be added to projects
  - Dependencies
  - Tasks

To add configuration to an existing project

```gradle
project(":<name>") {
  // configurations
}
```

To add shared configurations to all projects

```gradle
allprojects {
  // configurations
}
```

To add shared configurations to all subprojects

```
subprojects {
  // configurations
}
```

### Dependencies

```gradle
project(":<name>") {
  dependencies {
    api 'external'
    api project('project')
    implementation 'external'
    implementation project('project')
  }
}
```

- If a project uses an `api` dependency, then consumers of the projects would
  also depend on the api dependency
- If a project uses an `implementation` dependency, then consumers of the
  project would not depend on the implementation dependency
