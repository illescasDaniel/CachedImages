## CachedImages

An easy class to manage online images in Swift.

Main features:

* UIImages from online images (URL)

* Save images offline for later use (cache)

### Examples

```swift
CachedImages.shared.load(image: "https://test.com/image.jpg", into: imageView)
```

```swift
CachedImages.shared
    .load(image: "imageurl")
    .placeholder(image: UIImage())
    .into(imageView: UIImageView())
```

```swift
CachedImages.shared.load(url: fullQuestion.imageURL ?? "", onSuccess: { cachedImage in
	  self.activityIndicatorView.stopAnimating()
	  self.questionImageButton.setImage(cachedImage, for: .normal)
	  self.questionImageButton.isHidden = false
  }, prepareForDownload: {
	  self.questionImageButton.isHidden = true
	  self.activityIndicatorView.startAnimating()
  }, onError: { _ in
	  self.questionImageButton.isHidden = true
	  self.activityIndicatorView.stopAnimating()
})
```
