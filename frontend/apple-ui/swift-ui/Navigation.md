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

## Navigation Styles

- `StackNavigationViewStyle`: compact width devices (ex. iPhone)
- `DoubleColumnNavigationViewStyle`: wide width devices (ex. Mac)

`NavigationView` would pick what's best for the platform by default

# Three-Column Layout

To implement a three-column layout

- Use one root `NavigationView` with three children
  - One will be the first column, the sidebar
  - The other two will be place holders for the second and the third column;
    **If the placeholders are not present**, then the second column will appear
    as disabled
- In the first column, set up `NavigationLink` that lead to the second column
- In the second column, set up `NavigationLink` that lead to the third column

```swift
import SwiftUI

struct ThirdColumn: View {
  var body: some View {
    Text("Third Column Content")
      .toolbar {
        Button("Share") {}
        Button("Delete") {}
      }
  }
}

struct SecondColumn: View {
  var body: some View {
    List {
      NavigationLink("Third", destination: ThirdColumn())
      NavigationLink("Third", destination: ThirdColumn())
    }
    .navigationTitle(Text("Second Column"))
    .toolbar {
      Button("New") {}
    }
  }
}

struct FirstColumn: View {
  var body: some View {
    List {
      NavigationLink("Second", destination: SecondColumn())
      NavigationLink("Second", destination: SecondColumn())
    }
    .listStyle(SidebarListStyle())
  }
}

struct ContentView: View {
  var body: some View {
    NavigationView {
      FirstColumn()
      Text("Empty Second")
      Text("Empty Third")
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

# Resources

- [Triple Trouble](https://kean.blog/post/triple-trouble): how to do three
  column layout
