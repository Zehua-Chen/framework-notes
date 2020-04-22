# Motivation

Keep everything

- Debuggable
- Editable
- Modular
  - Scenes should be a blank-slate
  - Prefabs should not reference anything in a particular scene

# Solution

The general idea here is inversion of control (giving a component its
depdencies) , which can be implemented as

- Depedency Injection
- Scriptable Object
  - Use Unity Editor as a scriptable object

## Scriptable Object

[Video](https://www.youtube.com/watch?v=raQ3iHhE_Kk)

[Aricle](https://unity.com/how-to/architect-game-code-scriptable-objects)

A scriptable object (a scriptable object asset) is shared globally, and can be
referenced in the inspector

- This allows two components to read/write the same piece of data as long as
  they reference the same scriptable object
- When one component changes the data, the changes would reflect in the other
  components
- Components still have references, but these references are not scene-dependent
- Entire systems can be built in scriptable object, with the limitation of not
  having updates per frame
