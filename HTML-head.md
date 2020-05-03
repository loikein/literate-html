# `head` tag

<!-- MarkdownTOC -->

- [`title`](#title)
- [`base`](#base)
- [`link`](#link)
    - [CSS](#css)
    - [Favicon](#favicon)
    - [Apple Touch Icon](#apple-touch-icon)
- [`meta`](#meta)
    - [`charset`](#charset)
    - [Mobile Browser](#mobile-browser)
    - [iOS Specific](#ios-specific)
    - [Social Meta Tags](#social-meta-tags)

<!-- /MarkdownTOC -->

## `title`

## `base`

## `link`

### CSS

Avoid `<style>` tag if you can.

```html
<link rel="stylesheet" type="text/css" href="./modern-normalize.css">
<link rel="stylesheet" type="text/css" href="./style.css">
```

### Favicon

```html
<link rel="icon" type="image/x-icon" href="./favicon.ico">
```

### [Apple Touch Icon](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

If you want to provide different size image for each device, check sizes at [App Icon - Icons and Images - iOS - Human Interface Guidelines - Apple Developer](https://developer.apple.com/design/human-interface-guidelines/ios/icons-and-images/app-icon/).

```html
<link rel="apple-touch-icon" href="./touch-icon.png">
```

## `meta`

### `charset`

Set the character set of the page:

```html
<meta charset="UTF-8">
```

### Mobile Browser

What is viewport? [Configuring the Viewport - Safari Web Content Guide](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/UsingtheViewport/UsingtheViewport.html)

Let the page display according to mobile device size:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Note: at [MDN](https://developer.mozilla.org/zh-CN/docs/Mobile/Viewport_meta_tag), it is said that setting `initial-scale` constraints horizontal scrolling on mobile browsers, but this is NOT true for Safari. Use `transform: translate3d(0,0,0);` in CSS instead. (See [my answer at StackOverflow](https://stackoverflow.com/questions/17767176/overflow-x-value-ignored-in-mobile-safari/61419378#61419378))

### iOS Specific

Make it a PWA:

```html
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
```

### [Social Meta Tags](https://moz.com/blog/meta-data-templates-123)

The whole social media tag thing is based on [The Open Graph protocol](https://ogp.me/), whose website covers basically everything you need to know.

[Universal card](https://ogp.me/#metadata):

```html
<meta property="og:title" content="The Rock" />
<meta property="og:type" content="video.movie" />
<meta property="og:url" content="http://www.imdb.com/title/tt0117500/" />
<meta property="og:image" content="http://ia.media-imdb.com/images/rock.jpg" />
```

[Twitter Summary Card](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/markup):

![](https://d1avok0lzls2w.cloudfront.net/uploads/blog/527aced7516076.09156119.jpg)

```html
<!-- generate the card (choose one): -->
<!-- Summary Card:
aspect ratio: 1:1
minimum dimensions: 144x144
minimum dimensions: 4096x4096 -->
<meta name="twitter:card" content="summary">

<!-- Summary Large Image Card:
aspect ratio: 2:1
minimum dimensions: 300x157
maximum dimensions: 4096x4096 -->
<!-- <meta name="twitter:card" content="summary_large_image"> -->

<!-- @ the publisher: -->
<meta name="twitter:site" content="@nytimes">

<!-- title: -->
<meta name="twitter:title" content="Parade of Fans for Houston’s Funeral">

<!-- @ the author: -->
<meta name="twitter:creator" content="@SarahMaslinNir">

<!-- page summary: -->
<meta name="twitter:description" content="The guest list and parade of limousines with celebrities emerging from them seemed more suited to a red carpet event in Hollywood or New York than than a gritty stretch of Sussex Avenue near the former site of the James M. Baxter Terrace public housing project here.">

<!-- Images must be less than 5MB in size. -->
<meta name="twitter:image" content="http://graphics8.nytimes.com/images/2012/02/19/us/19whitney-span/19whitney-span-articleLarge.jpg">
```
