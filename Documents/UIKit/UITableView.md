# UITableView

### Set content insets at the bottom of TableView
Useful when the bottom of tableview is behind some buttons/overlay:
```swift
    tableView.contentInset.top = 100
```

### TableView jumps while scrolling
Setting estimated section height to 0 might help:
```swift
  tableView.estimatedSectionHeaderHeight = 0
    tableView.estimatedSectionFooterHeight = 0
    tableView.estimatedRowHeight = 0
    tableView.rowHeight = UITableView.automaticDimension
```

Additionaly we can cache cell sizes:
```swift
  private var cellHeights = [IndexPath: CGFloat]()
  
    func tableView(
    _ tableView: UITableView,
    willDisplay cell: UITableViewCell,
    forRowAt indexPath: IndexPath
  ) {
    let frame = tableView.rectForRow(at: indexPath)
    cellHeights[indexPath] = frame.size.height
  }
  
    func tableView(
    _ tableView: UITableView,
    estimatedHeightForRowAt indexPath: IndexPath
  ) -> CGFloat {
    return cellHeights[indexPath] ?? 100.0
  }
```

### Updating timer in UITableViewCell

1. Update data source and call tableView.reloadData() causes whole tableview to reload
2. Update data source and reload cell at indexPath
3. Find cell in tableView.visibleCells and update value directly
```swift
        if let realtimeCell = self.tableView.visibleCells.last
            as? RouteDetailsRealTimeInfoTableViewCell {
          realtimeCell.configure(viewModel: viewModel)
        }
```

