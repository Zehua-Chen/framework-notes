# Items

## Appearance

- `image`: icon image
- `label`: a string under the icon
- `isNavigational`: a navigational item is placed before everything else,
  including the window title (ex. Finder)

## Interactions

- `action` must be set for a toolbar to be interactable

## Variants

### `NSTrackingSeparatorToolbarItem`

```swift
let toolbar = NSTrackingSeparatorToolbarItem(
  identifier: .sidebarTrackingSeparator,
  splitView: splitView!,
  dividerIndex: 1)
```

In full-size-content-view windows, split view's separator can span the entire
height of a window. A `NSTrackingSeparatorToolbarItem` **displays a separator**
in the toolbar that tracks the separator of the split view and **make sure other
items before an after it are positioned into their split view sections**

- By default, **a tracking separator would be provided for a full-height
  sidebar**
