# UIView

### Create custom UIView and fill it with another view
```swift
class MyCustomUIView: UIView {
	private let customView = ViewFactory.buildCustomView()

	override init(frame: CGRect) {
	    super.init(frame: frame)
	    setupView()
	  }

	  required init?(coder aDecoder: NSCoder) {
	    super.init(coder: aDecoder)
	    setupView()
	  }

	  private func setupView() {
	    self.translatesAutoresizingMaskIntoConstraints = false
	    customView.translatesAutoresizingMaskIntoConstraints = false
	    addSubview(customView)
	    customView.attachAnchors(to: self)
	}
}```
