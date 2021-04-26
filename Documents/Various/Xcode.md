# Xcode tips & tricks

1. **Generating class initializers**

```swift
class TestClass {
  var name: String
  var surname: String
  let title: String
}
```
* Select class name
* Editor -> Refactor -> Generate Memberwise Initializer 
```swift
class TestClass {
  internal init(name: String, surname: String, title: String) {
    self.name = name
    self.surname = surname
    self.title = title
  }
  
  var name: String
  var surname: String
  let title: String
}
```

2. **Fixing all issues at once**
<img src="images/Xcode_2_1.png" width="80%">

* Instead of fixing errors one by one we can click **Editor -> Fix All Issues**
 


