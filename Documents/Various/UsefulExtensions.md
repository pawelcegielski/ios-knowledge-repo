# Useful Extensions

### Collection
#### Access collection element safely
```swift
extension Collection {

    /// Returns the element at the specified index if it is within bounds, otherwise nil.
    subscript (safe index: Index) -> Element? {
        return indices.contains(index) ? self[index] : nil
    }
}
```

### UIView
#### Attach view inside another view with insets
```swift
extension UIView {
  func attachAnchors(to view: UIView, with insets: UIEdgeInsets = .zero) {
    NSLayoutConstraint.activate([
      topAnchor.constraint(equalTo: view.topAnchor, constant: insets.top),
      rightAnchor.constraint(equalTo: view.rightAnchor, constant: -insets.right),
      bottomAnchor.constraint(equalTo: view.bottomAnchor, constant: -insets.bottom),
      leftAnchor.constraint(equalTo: view.leftAnchor, constant: insets.left)
    ])
  }
}
```


