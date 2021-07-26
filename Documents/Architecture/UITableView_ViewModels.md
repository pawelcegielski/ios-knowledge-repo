# UITableView - multiple view models

### UITableView + MVVM

How to use multiple view models to populate table view with custom cells. 

It enables adding multiple rows of different data and table view will automatically generate all cells based on view model type.

```swift
protocol AnimalViewModel {
  var age: Int
}
```

```swift
struct DogViewModel: AnimalViewModel {
  var isHappy: Bool
}

struct CatViewModel: AnimalViewModel {
  var isSleeping: Bool
}
```



```swift
override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {

switch animalInfoStruct {
  case let vm as CatViewModel:
  guard let cell = tableView.dequeue(
    CatCell.self,
    for: indexPath
  ) else {
    return UITableViewCell()
}
  cell.setUp(vm)
  return cell
}
case let vm as DogViewModel
  guard let cell = tableView.dequeue(
    CatCell.self,
    for: indexPath
  ) else {
    return UITableViewCell()
  }
    cell.setUp(vm)
    return cell
}
```
