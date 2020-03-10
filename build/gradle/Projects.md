# Projects

Subprojects must be included in the `settings.gradle` file

```gradle
include 'console', `other`
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

### Dependencies

```gradle
project(":<name>") {
  dependencies {
    api `project`
    implementation `project`
  }
}
```

- If a project uses an `api` dependency, then consumers of the projects would
  also depend on the api dependency
- If a project uses an `implementation` dependency, then consumers of the
  project would not depend on the implementation dependency
