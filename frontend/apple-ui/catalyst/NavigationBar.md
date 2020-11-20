# Navigation Bar

Navigation bar should be hidden on the mac

```swift
class ViewController {
  override func viewDidLoad() {
    super.viewDidLoad()

    if traitCollection.userInterfaceIdiom == .mac {
      navigationController?.setNavigationBarHidden(true, animated: false)
    }
  }
}
```
