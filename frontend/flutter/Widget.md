# Rendering

Flutter maintains three trees

- **Widget tree**:
  - Holds config for a piece of UI
  - Has public API
- **Element tree**:
  - Represents an actual piece of UI
  - Holds refs, manages trees (life cycle)
- **Render object tree**:
  - Knows about size, layout painting and compositing

[How Flutter Renders Widgets](https://www.youtube.com/watch?v=996ZgFRENMs)
