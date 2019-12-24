# Concepts

## Actions

### Action Type

- Value: monitor changes to controls bound to the action, but only take the most
  activated one driving the action and only report values of that control
  - When enabled initially, perform state check of all bound controls and report
    values of the activated controls
- Button: similar to `Value`, but only bound to `ButtonControl`, does not
  perform initial check
- Pass through: similar do `Value`, but does report all values of all controls
  bound to an action

## Bindings

- **Bindings** trigger actions by
  - Feeding the action with values
- **Path** The hardware event that make the make the binding fire

### Binding Composite

- Binding to a single path only produces one value
- **Binding composite** composes a complex type from different children bindings
- Two children composite can perform the same compositions
  - Up arrow
  - W

### Interactions

- Interactions configure how the binding would trigger the actions (ex. hold)

## Control Scheme

- A way to group bindings to target different input devices

## Action Maps

- **Actions maps** are collections of actions
- Actions in the map can be edited at run time

## Actions (Asset)

An **action assets** is used to save the configurations of multiple action maps

# Consuming Inputs

## Player Input (Component)

- A "Player Input" object can be attached to a game object that would handle the
  following automatically
  - Scheme switching
  - Default map
  - Event firing (fire on Monobehavior objects)
  - Local multiplayer (including split screen)

## `IInputActionCollection` Generation

An implementation of `IInputActionCollection` can be generated from the asset
file that can be used to listen to the inputs

- Instances **must be explictly enabled**
