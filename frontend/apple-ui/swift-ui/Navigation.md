# Overview

```swift
struct TodoDetail: View {
  var todo: String

  var body: some View {
    NavigationView {
      NavigationLink("A", destination: Text("Child A"))
      NavigationLink("B", destination: Text("Child B"))
    }
  }
}
```

Navigation involves two components `NavigationView` and `NavigationLink`

- `NavigationView` must be the parent of `NavigationLink`
- Works on all platforms their navigation styles

# Navigation Styles

- `StackNavigationViewStyle`: compact width devices (ex. iPhone)
- `DoubleColumnNavigationViewStyle`: wide width devices (ex. Mac)

`NavigationView` would pick what's best for the platform by default

# Three-Column Layout

To implement a three-column layout, simply neste a navigation view inside
another navigation view

```swift
struct TodoDetail: View {
  var todo: String

  var body: some View {
    NavigationView {
      NavigationView {
        NavigationLink("A", destination: Text("Child A"))
      }
      NavigationLink("B", destination: Text("Child B"))
    }
  }
}
```

# Programatic Control

## Presenting Views

```swift
struct ContentView: View {
  @State
  var todos: [String] = ["Todo 1", "Todo 2"]

  @State
  var selection: String? = nil

  var body: some View {
    NavigationView {
      List {
        ForEach(todos, id: \.self) { todo in
          NavigationLink(
            todo, destination: TodoDetail(todo: todo), tag: todo, selection: $selection)
        }
        .onDelete { path in
          withAnimation {
            todos.remove(atOffsets: path)
          }
        }
      }
      .listStyle(SidebarListStyle())
      .navigationTitle("Todos")
    }
  }
}
```

`NavigationLink` offers two sets of parameters that enable programmatic control
of navigation

- `tag` and `selection`
- `isActive`

## Dismissing Views

`PresentationMode.dismiss(self:)` eanbles the programmtic dismiss of a view

- Accessed via `@Environment(\.presentationMode)`
