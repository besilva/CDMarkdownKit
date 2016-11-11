# CDMarkdownKit

[![CI Status](http://img.shields.io/travis/chrisdhaan/CDMarkdownKit.svg?style=flat)](https://travis-ci.org/chrisdhaan/CDMarkdownKit)
[![Version](https://img.shields.io/cocoapods/v/CDMarkdownKit.svg?style=flat)](http://cocoapods.org/pods/CDMarkdownKit)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![License](https://img.shields.io/cocoapods/l/CDMarkdownKit.svg?style=flat)](http://cocoapods.org/pods/CDMarkdownKit)
[![Platform](https://img.shields.io/cocoapods/p/CDMarkdownKit.svg?style=flat)](http://cocoapods.org/pods/CDMarkdownKit)

This pod is currently in development. As of release 0.9.0 the code is stable and in a usable state to install in applications.

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

---

## Requirements

- iOS 8.0 or higher

---

## Installation

### Installation via CocoaPods

CDMarkdownKit is available through [CocoaPods](http://cocoapods.org). CocoaPods is a dependency manager that automates and simplifies the process of using 3rd-party libraries like CDMarkdownKit in your projects. You can install CocoaPods with the following command:

```ruby
gem install cocoapods
```

To integrate CDMarkdownKit into your Xcode project using CocoaPods, simply add the following line to your Podfile:

```ruby
pod "CDMarkdownKit"
```

Afterwards, run the following command:

```ruby
pod install
```

### Installation via Carthage

CDMarkdownKit is available through [Carthage](https://github.com/Carthage/Carthage). Carthage is a decentralized dependency manager that builds your dependencies and provides you with binary frameworks.

You can install Carthage via [Homebrew](http://brew.sh) with the following command:

```ruby
brew update
brew install carthage
```

To integrate CDMarkdownKit into your Xcode project using Carthage, simply add the following line to your Cartfile:

```ruby
github "chrisdhaan/CDMarkdownKit"
```

Afterwards, run the following command:

```ruby
carthage update
```

---

## Usage

### Initialization

```swift
// Create parser
let markdownParser = CDMarkdownParser()
// Parse markdown
let markdown = "This *framework* helps **with** parsing `markdown`."
label.attributedText = markdownParser.parse(markdown)
```

### Customization

```swift
// Create parser
let markdownParser = CDMarkdownParser(font: UIFont(name: "HelveticaNeue", size: 16),
                                      boldFont: UIFont(name: "HelveticaNeue-Bold", size: 16),
                                      italicFont: UIFont(name: "HelveticaNeue-Thin", size: 16),
                                      fontColor: UIColor.darkGray,
                                      backgroundColor: UIColor.lightGray)
// Customize elements
/// Bold
markdownParser.bold.color = UIColor.cyan
markdownParser.bold.backgroundColor = UIColor.purple
/// Header
markdownParser.header.color = UIColor.black
markdownParser.header.backgroundColor = UIColor.orange
/// List
markdownParser.list.color = UIColor.black
markdownParser.list.backgroundColor = UIColor.red
/// Quote
markdownParser.quote.color = UIColor.gray
markdownParser.quote.backgroundColor = UIColor.clear
/// Link
markdownParser.link.color = UIColor.blue
markdownParser.link.backgroundColor = UIColor.green
markdownParser.automaticLink.color = UIColor.blue
markdownParser.automaticLink.backgroundColor = UIColor.green
/// Italic
markdownParser.italic.color = UIColor.gray
markdownParser.italic.backgroundColor = UIColor.clear
/// Code
markdownParser.code.font = UIFont.systemFont(ofSize: 17)
markdownParser.code.color = UIColor.red
markdownParser.code.backgroundColor = UIColor.black
/// Syntax
markdownParser.syntax.font = UIFont.systemFont(ofSize: 15)
markdownParser.syntax.color = UIColor.lightGray
markdownParser.syntax.backgroundColor = UIColor.black
// Parse markdown
let markdown = "This *framework* helps **with** parsing `markdown`."
label.attributedText = markdownParser.parse(markdown)
```

### Supported Elements

```
*italic* or _italic_
**bold** or __bold__

# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6

> Quote

* List
- List
+ List

`code`

```syntax```

[Link](url)
```

---

## Author

Christopher de Haan, contact@christopherdehaan.me

## Credits

CDMarkdownKit was influenced by [MarkdownKit](https://github.com/ivanbruel/MarkdownKit), a markdown parsing library developed by Ivan Bruel.

## License

CDMarkdownKit is available under the MIT license. See the LICENSE file for more info.

---