# Layout

## List Layout

```swift
let configuration = UICollectionLayoutListConfiguration(appearance: .insetGrouped)
let layout = UICollectionViewCompositionalLayout.list(using: configuration)
```

- If a list layout is used, `UICollectionViewListCell` should be as the cell

## Swipe Actions

```swift
configuration.trailingSwipeActionsConfigurationProvider = { indexPath in
  let delete = UIContextualAction(style: .destructive, title: "Delete") {
    _, _, complete in
    let course = self.dataSource.itemIdentifier(for: indexPath)!
    var snapshot = self.dataSource.snapshot()
    snapshot.deleteItems([course])

    self.dataSource.apply(snapshot)
    complete(true)
  }

  return UISwipeActionsConfiguration(actions: [delete])
}
```

`UICollectionLayoutListConfiguration` contains the following callbacks for
handlign swipe actions

- `trailingSwipeActionsConfigurationProvider`
- `leadingSwipeActionsConfigurationProvider`

# Cells

## Configuring Cells

```swift
courseCellRegistration = UICollectionView.CellRegistration<CourseViewCell, Course> {
  cell, indexPath, course in
  var configuration = cell.defaultContentConfiguration()
  configuration.text = course.name

  cell.contentConfiguration = configuration
}
```

Cell registrations are done by instantiating a
`UICollectionView.CellRegistration`. The instantiated object is then used to
obtain cells

- The callback is used to update cell's contents

### Accessories

Accessories can be added using

```swift
cell.accessories = [
  .disclosureIndicator(),
  .checkmark()
]
```

The cell would automaticall sort the accessories' orders

## Obtaining Cells

```swift
dataSource = UICollectionViewDiffableDataSource<CourseType, Course>(
  collectionView: collectionView
) { collectionView, indexPath, course in
  let cell = collectionView.dequeueConfiguredReusableCell(
    using: self.courseCellRegistration, for: indexPath, item: course)

  return cell
}
```

Cells can be obtained by calling `dequeueConfiguredReusableCell`. No further
configuration is needed, which has already been handled by
`UICollectionView.CellRegistration`
