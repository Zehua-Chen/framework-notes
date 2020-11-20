macOS sidebars has the following characteristics

- Translucent background
- Full height (from Big Sur)

The view controller used as the sidebar are typically the "master view
controller" of `UISplitViewController`

# Translucent Background

Translucenet background can be enabled using the following snippet

```swift
splitViewController.primaryBackgroundStyle = .sidebar
```

# Full Height

If a view controller does not have a visible navigation bar, it is automatically
displayed as full height

```swift
self.navigationController?.setNavigationBarHidden(true, animated: true)
```

# `UITableViewController` as Sidebar

The following styles would implement a sidebar where each row would have a
tinted background, i.e. non-grey

- Grouped
- Inset Grouped

# Collapsing/Expanding the Sidebar

Add a `NSToolbarItem.Identifier.toggleSidebar` toolbar item to the toolbar. This
toolbar item automatically implement the collapsing and expanding of the
sidebars
