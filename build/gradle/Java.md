# Java

To support java, apply plugins using

```gradle
plugins {
  id 'java'
}
```

The java plugin addes the following tasks

- `Jar`

## `Jar`

```gradle
jar {
  manifest {
    // manifest
  }
}
```

- To produce an executable jar, add `attributes "Main-Class": "Program"`
