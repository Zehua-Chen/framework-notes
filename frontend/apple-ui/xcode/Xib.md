# Overview

A xib file contains multiple user interface items and is compiled to nib files
during the build process

- **File Owner**: file owner manages the links between the user interface items
  and the code

# Custom View

```swift
import UIKit

class CustomView: UIView {
  @IBOutlet
  weak var label: UILabel!

  override init(frame: CGRect) {
    super.init(frame: frame)
    addSubviews()
  }

  required init?(coder: NSCoder) {
    super.init(coder: coder)
    addSubviews()
  }

  fileprivate func addSubviews() {
    let subview = Bundle.main.loadNibNamed(
      "CustomView", owner: self, options: nil)?.first as! UIView

    addSubview(subview)

    subview.translatesAutoresizingMaskIntoConstraints = false

    subview.leftAnchor.constraint(equalTo: leftAnchor).isActive = true
    subview.rightAnchor.constraint(equalTo: rightAnchor).isActive = true
    subview.topAnchor.constraint(equalTo: topAnchor).isActive = true
    subview.bottomAnchor.constraint(equalTo: bottomAnchor).isActive = true
  }
}
```

- **Creating the Custom View**
  - Create a xib file with a view in it
  - Use the `CustomView` as the "File Owner" (CustomView has links to views in
    xib)
  - Load the views of the nib file in `CustomView`'s initializers
    - Don't forget to assign owner as `self`
- **Using the Custom View**: instantiate custom view
