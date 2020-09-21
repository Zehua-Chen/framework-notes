# Dependencies

```gradle
dependencies {
  api 'external'
  api project('project')
  implementation 'external'
  implementation project('project')
  compileOnly 'external'
  compileOnly project('project')
  runtimeOnly 'external'
  runtimeOnly project('project')
  testX 'external'
  testX project('project')
}
```

- If a project uses an `api` dependency, then consumers of the projects would
  also depend on the api dependency
- If a project uses an `implementation` dependency, then consumers of the
  project would not depend on the implementation dependency
- testX are only used for test builds
  - `testCompileOnly` needs to be added for every `compileOnly` otherwise there
    would be compiler errors (intellij annotations)

## External Dependencies

Externa depdencies are fetched from repositories

```gradle
repositories {
  mavenCentral()
}
```
