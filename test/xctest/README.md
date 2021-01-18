# Primary APIs

## `XCTestCase`

```swift
import XCTest

final class MyTest: XCTestCase {
  // Run at the beginning of each test case
  override class func setUp() {
    super.setUp()
  }

  // Run at the end of each test case
  override class func tearDown() {
    super.tearDown()
  }

  // Run at the beginning of each test method
  override func setUp() {
    super.setUp()
  }

  // Run at the end of each test method
  override func tearDown() {
    super.tearDown()
  }

  func testFoo() {
  }

  func testBoo() {
  }
}
```

A test case is defined to be a class that subclass `XCTestCase`

- Test functions must start with `test`
