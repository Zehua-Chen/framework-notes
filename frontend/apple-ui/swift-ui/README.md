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

# Data Flow

Memory of states asscoiated with views are only allocated after the view has
been added to the view hierarchy. Therefore, there are only two ways to
initialize states

- In callbacks that are invoked when a view has been added to the view
  hierarchy, like `onAppear`

  ```swift
  import SwiftUI

  struct Foo: View {
    @State
    var state: Int

    var body: some View {
      Text("")
        .onAppear {
          state = 0
        }
    }
  }
  ```

- Using `init(initialValue:)` of property wrappers

  ```swift
  import SwiftUI

  struct Foo: View {
    @State
    var state: Int = 0 // will use State.init(initialValue:)

    var body: some View {
      ...
    }
  }
  ```
