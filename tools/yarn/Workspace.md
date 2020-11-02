# Workspace

Workspace is defined by a root `package.json` with the following fields

```json
{
  "private": true,
  "workspaces": ["packages/*"]
}
```

- Projects in a workspace share the same
  - `node_modules`
  - `yarn.lock`
  - `dependencies` and `devDependencies` in root `package.json`
- Projects in a workspace are all automatically linked to the root
  `node_modules`
