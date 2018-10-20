---
layout: base
---

Below are the font and point sizes used by iOS at the default sizing level. You can read more, including about the accessibility curves, on [Apple's documentation](https://developer.apple.com/design/human-interface-guidelines/ios/visual-design/typography).

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

Use the style like:

```swift
label.font = UIFont.preferredFont(forTextStyle: .body)
```

If you want to modify the font size a little bit, dynamically change it like:

```swift
let desc = UIFontDescriptor.preferredFontDescriptor(withTextStyle: .body)
label.font = UIFont.systemFont(ofSize: desc.pointSize - 1.0, weight: .regular)
```

Get dynamic type scaling with a custom font like:

```swift
// you can also hard-code point sizes per style, if Apple's are far off
let desc = UIFontDescriptor.preferredFontDescriptor(withTextStyle: .body)
let baseFont = UIFont(name: "Avenir", size: desc.pointSize)!

let metrics = UIFontMetrics(forTextStyle: .body)
metrics.scaledFont(for: baseFont)
```