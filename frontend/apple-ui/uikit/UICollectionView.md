# Layout

## List Layout

```swift
let configuration = UICollectionLayoutListConfiguration(appearance: .insetGrouped)
let layout = UICollectionViewCompositionalLayout.list(using: configuration)
```

- If a list layout is used, `UICollectionViewListCell` should be as the cell

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
