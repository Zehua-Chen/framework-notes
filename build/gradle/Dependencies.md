# Dependencies

```gradle
dependencies {
  api 'external'
  api project('project')
  implementation 'external'
  implementation project('project')
}
```

- If a project uses an `api` dependency, then consumers of the projects would
  also depend on the api dependency
- If a project uses an `implementation` dependency, then consumers of the
  project would not depend on the implementation dependency

## External Dependencies

Externa depdencies are fetched from repositories

```gradle
repositories {
  mavenCentral()
}
```
