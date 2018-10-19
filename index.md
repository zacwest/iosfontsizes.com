---
layout: home
---

<a href="https://github.com/zacwest/iosfontsizes.com"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_right_red_aa0000.png" alt="Fork me on GitHub"></a>

At the default sizing level, these are the font and point sizes iOS assigns:

| Style          | Size | Font              |
| -------------- | ---- | ----------------- |
| .largeTitle  | 34.0 | SFUIDisplay       | 
| .title1      | 28.0 | SFUIDisplay (-Light on iOS ≤10) |
| .title2      | 22.0 | SFUIDisplay       | 
| .title3      | 20.0 | SFUIDisplay       | 
| .headline    | 17.0 | SFUIText-Semibold | 
| .callout     | 16.0 | SFUIText          | 
| .subheadline | 15.0 | SFUIText          | 
| .body        | 17.0 | SFUIText          | 
| .footnote    | 13.0 | SFUIText          | 
| .caption1    | 12.0 | SFUIText          | 
| .caption2    | 11.0 | SFUIText          | 

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