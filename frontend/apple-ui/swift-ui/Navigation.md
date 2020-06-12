# macOS

- Starts with a `NavigationView` as root
- `NavigationView` contains two children
  - A master
  - A detail
- The **master** view must contain a `List` element in its children. There are
  two approaches
  - Using `NavigationLink`
  - Not using `NavigationLink`
- The **detail** view needs to provide a height and width (or minimum height and
  and width), otherwise NavigationView would pick a height and a width.

```swift
struct ContentView: View {
  var body: some View {
    NavigationView {
      VStack {
        Filter()
        EmailList()
      }

      EmailContent()
    }
  }
}
```

## Master View

### No Navigation Link

- `List(selection:)` would enable selecting rows
  - Use `ForEach` if content is dynamically generated

```swift
struct ContentView: View {
  @State selection: Int? = 0

  var body: some View {
    NavigationView {
      VStack {
        Filter()

        List(selection: $selection) {
          ForEach(emails) { email in
            EmailRow(email)
          }
        }
      }

      EmailContent()
    }
  }
}
```

### Navigation Link

- Detail view is optional, since NavigationLink provides one
  - If a detail view on the root level is still available, it would be used when
    nothing is selected
- Don't have to use `List(selection:)` to enable selection

```swift
struct ContentView: View {
  var body: some View {
    NavigationView {
      VStack {
        Filter()

        List {
          ForEach(emails) {
            NavigationLink(EmailContent(), label: { Text("Email") })
          }
        }
      }

      DefaultEmailContent()
    }
  }
}
```

# iOS

TODO:
