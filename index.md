---
layout: home
---

<a href="https://github.com/zacwest/iosfontsizes.com"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_right_red_aa0000.png" alt="Fork me on GitHub"></a>

At the default sizing level, these are the font and point sizes iOS assigns:

| Style        | Font               | Size | 
| ------------ | ------------------ | ---- | 
| .largeTitle  | SFUIDisplay       | 34.0 | 
| .title1      | SFUIDisplay <br> (-Light on iOS <=10) | 28.0 |
| .title2      | SFUIDisplay       | 22.0 |
| .title3      | SFUIDisplay       | 20.0 |
| .headline    | SFUIText-Semibold | 17.0 |
| .callout     | SFUIText          | 16.0 |
| .subheadline | SFUIText          | 15.0 |
| .body        | SFUIText          | 17.0 |
| .footnote    | SFUIText          | 13.0 |
| .caption1    | SFUIText          | 12.0 |
| .caption2    | SFUIText          | 11.0 |

You can read more, including about the accessibility curves, on [Apple's documentation](https://developer.apple.com/design/human-interface-guidelines/ios/visual-design/typography). 

Use the style with code like:

```swift
label.font = UIFont.preferredFont(forTextStyle: .body)
```

If you want to modify the font size a little bit, dynamically change it like:

```swift
let desc = UIFontDescriptor.preferredFontDescriptor(withTextStyle: .body)
label.font = UIFont.systemFont(ofSize: desc.pointSize - 1.0, weight: .regular)
```