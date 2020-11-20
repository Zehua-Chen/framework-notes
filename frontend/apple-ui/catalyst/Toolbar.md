# Creating Toolbar

Toolbars can be created in `SceneDelegate`

```swift
class SceneDelegate {
  func scene(
      _ scene: UIScene,
      willConnectTo session: UISceneSession,
      options connectionOptions: UIScene.ConnectionOptions) {
    // Use this method to optionally configure and attach the UIWindow `window`
    // to the provided UIWindowScene `scene`.
    //
    // If using a storyboard, the `window` property will automatically be
    // initialized and attached to the scene.
    //
    // This delegate does not imply the connecting scene or session are new
    // (see `application:configurationForConnectingSceneSession` instead).
    guard let windowScene = (scene as? UIWindowScene) else { return }

    #if targetEnvironment(macCatalyst)
    self.toolbar = NSToolbar()
    self.toolbarDelegate = ToolbarDelegate()
    self.toolbar?.delegate = self.toolbarDelegate

    if let titlebar = windowScene.titlebar {
      titlebar.titleVisibility = .hidden
      titlebar.toolbar = self.toolbar
      titlebar.toolbarStyle = .automatic
    }
  }
}
```
