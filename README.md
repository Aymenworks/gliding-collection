[![header](/assets/header.png)](https://business.ramotion.com?utm_source=gthb&utm_medium=special&utm_campaign=elongation-preview-logo)

[![Twitter](https://img.shields.io/badge/Twitter-@Ramotion-blue.svg?style=flat)](http://twitter.com/Ramotion)
[![PodPlatform](https://img.shields.io/cocoapods/p/GlidingCollection.svg)](https://cocoapods.org/pods/GlidingCollection)
[![PodVersion](https://img.shields.io/cocoapods/v/GlidingCollection.svg)](http://cocoapods.org/pods/GlidingCollection)
[![Documentation](https://img.shields.io/cocoapods/metrics/doc-percent/GlidingCollection.svg)](https://cdn.rawgit.com/Ramotion/elongation-preview/master/docs/index.html)

[![Carthage](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Ramotion/elongation-preview)
[![Codebeat](https://codebeat.co/badges/6a009992-5bf2-4730-aa35-f3b20ce7693d)](https://codebeat.co/projects/github-com-ramotion-elongation-preview)

<br>

## About
This project is maintained by Ramotion, Inc.<br>
We specialize in the designing and coding of custom UI for Mobile Apps and Websites.<br><br>**Looking for developers for your project?**

<a href="http://business.ramotion.com?utm_source=gthb&utm_medium=special&utm_campaign=elongation-preview-contact-us/#Get_in_Touch" > <img src="https://github.com/Ramotion/navigation-stack/raw/master/contact_our_team@2x.png" width="150" height="30"></a>

<!-- [![animation](/assets/GlidingCollection.gif)](https://dribbble.com/shots/3333066-Elongation-Preview-App-Interface-UX-UI) -->

The [iPhone mockup](https://store.ramotion.com?utm_source=gthb&utm_medium=special&utm_campaign=elongation-preview) available [here](https://store.ramotion.com?utm_source=gthb&utm_medium=special&utm_campaign=elongation-preview).
<br>

## Requirements

- iOS 8.0+
- Xcode 8
- Swift 3

<br>

## Installation
You can install `GlidingCollection` in several ways:

- Add source files to your project.

<br>

- Use [CocoaPods](https://cocoapods.org):
``` ruby
pod 'GlidingCollection'
```

<br>

- Use [Carthage](https://github.com/Carthage/Carthage):
```
github "Ramotion/gliding-collection"
```

<br>

## How to use

• Create some view controller class:

```swift
import GlidingCollection

class ViewController: UIViewController {
  let items = ["shirts", "pants", "vests"]
}
```

• Drag `UIView` onto the canvas, change it's class to `GlidingCollection` and set autolayout constraints.

![step-2](/assets/step-2.png)

• Connect this view to your view controller class as `@IBOutlet`.

```swift
@IBOutlet var glidingCollection: GlidingCollection!
```

• Make your view controller conformant to `GlidingCollectionDatasource`. It's very similar to `UITableView` or `UICollectionView` *datasource* protocols that you know:

```swift
extension ViewController: GlidingCollectionDatasource {

  func numberOfItems(in collection: GlidingCollection) -> Int {
    return items.count
  }

  func glidingCollection(_ collection: GlidingCollection, itemAtIndex index: Int) -> String {
    return "– " + items[index]
  }

}
```

• Make your view controller conformant to `UICollectionViewDatasource`:

```swift
extension ViewController: UICollectionViewDatasource {
  
  func collectionView(_ collectionView: UICollectionView, numberOfItemsInSection section: Int) -> Int {
    let section = glidingView.expandedItemIndex // Value of expanded section.
    return images[section].count
  }
  
  func collectionView(_ collectionView: UICollectionView, cellForItemAt indexPath: IndexPath) -> UICollectionViewCell {
    guard let cell = collectionView.dequeueReusableCell(withReuseIdentifier: "Cell", for: indexPath) as? CollectionCell else { return UICollectionViewCell() }
    // Configure and return your cell.
    return cell
  }
  
}
```

## Customize

You can customize appearance of `GlidingCollection` by overriding `GlidingCollection`'s `shared` instance with your own one.

```swift
var config = GlidingConfig.shared
config.buttonsFont = UIFont.boldSystemFont(ofSize: 22)
config.activeButtonColor = .black
config.inactiveButtonsColor = .lightGray
GlidingConfig.shared = config
```

>🗒 All parameters with their descriptions listed in [`GlidingConfig`](/GlidingCollection/GlidingConfig.swift) file.

<br>

## Notes

There are [`GlidingCollectionDelegate`](/GlidingCollection/Protocols/GlidingCollectionDelegate.swift) protocol which can you notify when *item* in `GlidingCollection` `didSelect`, `willExpand` and `didExpand`.

<br>

## License

GlidingCollection is released under the MIT license.
See [LICENSE](./LICENSE) for details.

<br>

## Follow us

[![Twitter URL](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=https://github.com/ramotion/elongation-preview)
[![Twitter Follow](https://img.shields.io/twitter/follow/ramotion.svg?style=social)](https://twitter.com/ramotion)