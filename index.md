---
layout: base
---

# iOS Font Sizes

Below are the font and point sizes used by iOS at the default sizing level. You can read more, including about the accessibility curves, on [Apple's documentation](https://developer.apple.com/design/human-interface-guidelines/ios/visual-design/typography).

| .largeTitle  | **34.0** | SFUIDisplay       | 
| .title1      | **28.0** | SFUIDisplay <small>(-Light ≤ iOS 10)</small> |
| .title2      | **22.0** | SFUIDisplay       | 
| .title3      | **20.0** | SFUIDisplay       | 
| .headline    | **17.0** | SFUIText-Semibold | 
| .subheadline | **15.0** | SFUIText          | 
| .body        | **17.0** | SFUIText          | 
| .callout     | **16.0** | SFUIText          | 
| .footnote    | **13.0** | SFUIText          | 
| .caption1    | **12.0** | SFUIText          | 
| .caption2    | **11.0** | SFUIText          | 

## Usage

Use `preferredFont(forTextStyle:)` or `scaledFont(for:)` with the `UIFont.TextStyle` constants instead of hard-coding font values in your code.

```swift
// update when the user changes their settings
label.adjustsFontForContentSizeCategory = true
label.font = UIFont.preferredFont(forTextStyle: .body)
```

You can use a modified version of the font with the same scaling:

```swift
// use a 16.0 font instead of 17.0 for body, at normal sizing
let adjustedFont = UIFont.systemFont(ofSize: 16.0, weight: .regular)

// use the scaled font version so it still updates automatically
label.adjustsFontForContentSizeCategory = true
label.font = UIFontMetrics(forTextStyle: .body).scaledFont(for: adjustedFont)
```

This will give you a body point with the default size at `16.0`. To use a different font family, change the `systemFont(ofSize:weight:)` call.