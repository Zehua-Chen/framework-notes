# Appearnce

## Title, Subtitle

```swift
// self.view.window is of NSWindow
self.view.window?.title = ""
self.view.window?.subtitle = ""
```

- `title`:
  - Available in Interface Builder
- `subtitle`:
  - Available in Interface Builder

When the top bar has compact height, it would adopt the following look

```
title - subtitle
```

Otherwise, it would adopt the following look

```
title
subtitle
```
