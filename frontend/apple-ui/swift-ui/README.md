# Concepts

- **Views**: a piece of the interface
- **Scenes**: a presentation of views in distinct regions, i.e. windows
  - on macOS, scenes can be presented as tabs
  - `DocumentGroup`
  - `WindowGroup`
  - `Settings` (macOS only)
- **Apps**: scenes make up apps

## Apps

```swift
@main
struct MyApp: App {
  var body: some Scene {
    WindowGroup {
      SomeView()
    }
  }
}
```
