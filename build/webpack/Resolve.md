# Resolve

`extensions`

By defualt, webpack do not look for typescript files, to fix this, use

```ts
resolve: {
  extensions: [".ts", ".js"],
}
```
