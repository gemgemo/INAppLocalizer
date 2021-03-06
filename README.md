# INAppLocalizer

[![CI Status](http://img.shields.io/travis/gemgemo/INAppLocalizer.svg?style=flat)](https://travis-ci.org/gemgemo/INAppLocalizer)
[![Version](https://img.shields.io/cocoapods/v/INAppLocalizer.svg?style=flat)](http://cocoapods.org/pods/INAppLocalizer)
[![License](https://img.shields.io/cocoapods/l/INAppLocalizer.svg?style=flat)](http://cocoapods.org/pods/INAppLocalizer)
[![Platform](https://img.shields.io/cocoapods/p/INAppLocalizer.svg?style=flat)](http://cocoapods.org/pods/INAppLocalizer)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

## Installation

INAppLocalizer is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'INAppLocalizer'
```

## Usage

```swift

import UIKit
import INAppLocalizer

class ViewController: UIViewController, Localizer {

    override func viewDidLoad() {
        super.viewDidLoad()
        NotificationCenter.default.addObserver(self,
                                               selector: #selector(onLanguageDidChanged),
                                               name: .languageDidChanged, object: nil)
        print(INAppLocalizer.current)
        print(INAppLocalizer.getSelectedLanguages())
        INAppLocalizer.set(language: "ar")
    }

    @objc func onLanguageDidChanged() {
        let language = localize(for: LocalizationsKeys.language)
        print(#function, language)
    }

}

enum LocalizationsKeys: String, LocalizedKey {
    case language = "langauge.lan"
}

```


## Author

Gamal, gamalal3yk@gmail.com

## License

INAppLocalizer is available under the MIT license. See the LICENSE file for more info.
