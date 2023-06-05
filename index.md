---
layout: base
---

# iOS Font Sizes

Below are the font and point sizes used by iOS at the default sizing level. You can read more, including about the accessibility curves, on [Apple's documentation](https://developer.apple.com/design/human-interface-guidelines/ios/visual-design/typography).

| .extraLargeTitle<br><small>iOS 17</small>  | **36.0** | SFUI-Bold |
| .extraLargetitle2<br><small>iOS 17</small> | **28.0** | SFUI-Bold |
| .largeTitle       | **34.0** | SFUI-Regular  | 
| .title1           | **28.0** | SFUI-Regular  | 
| .title2           | **22.0** | SFUI-Regular  | 
| .title3           | **20.0** | SFUI-Regular  | 
| .headline         | **17.0** | SFUI-Semibold | 
| .subheadline      | **15.0** | SFUI-Regular  | 
| .body             | **17.0** | SFUI-Regular  | 
| .callout          | **16.0** | SFUI-Regular  | 
| .footnote         | **13.0** | SFUI-Regular  | 
| .caption1         | **12.0** | SFUI-Regular  | 
| .caption2         | **11.0** | SFUI-Regular  | 

## Usage

Use `preferredFont(forTextStyle:)` or `scaledFont(for:)` with the `UIFont.TextStyle` constants instead of hard-coding font values in your code.

```swift
// update when the user changes their settings
label.adjustsFontForContentSizeCategory = true
label.font = UIFont.preferredFont(forTextStyle: .body)
```

You can use a modified version of the font with the same scaling:

```swift
// for a custom font at the normal scaling
let adjustedFont = UIFont(name: "AmericanTypewriter", size: 17.0)

// for the system font, but starting at a different default point size
// this point size value must be defined as a constant, see below
let adjustedFont = UIFont.systemFont(ofSize: 16.0, weight: .regular)

// use the scaled font version so it still updates automatically
label.adjustsFontForContentSizeCategory = true
label.font = UIFontMetrics(forTextStyle: .body).scaledFont(for: adjustedFont)
```

**NOTE:** The current point size from `preferredFont(forTextStyle:)` already includes scaling. Using it as the starting point will produce double-scaled fonts at ridiculous point sizes.
