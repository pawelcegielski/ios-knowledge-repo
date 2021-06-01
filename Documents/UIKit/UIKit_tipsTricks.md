# UIKit Tips & Tricks

### Render image with tint
```swift
    func setImageColor(color: UIColor) {
            let templateImage = self.image?.withRenderingMode(UIImage.RenderingMode.alwaysTemplate)
            self.image = templateImage
            self.tintColor = color
        }
```

### Handling dates - hour/day/minute before/after
//Get one hour before now
```swift
let earlyDate = Calendar.current.date(
  byAdding: .hour, 
  value: -1, 
  to: Date())
```

### Animate view change

animate view.layoutIfNeeded() vs animate subview.layoutIfNeeded()

### Flip bool value
```swift
var isReady: Bool

isReady = !isReady
//or 
isReady.toggle()
```

