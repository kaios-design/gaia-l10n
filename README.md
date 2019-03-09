# l10n.js

The l10n.js lib used in Gaia, extracted from [mozilla-b2g/gaia](https://github.com/mozilla-b2g/gaia/blob/master/shared/js/l10n.js).

Please refer to
- [App localization](https://developer.mozilla.org/en-US/docs/Archive/B2G_OS/Firefox_OS_apps/Localization) - A detailed guide on FxOS app localization.

Gaia l10n derived a lot from original [webL10n](https://github.com/fabi1cazenave/webL10n). There's also [l20n](https://github.com/l20n/l20n.js), but it's rarely used (recommended from FxOS 2.5). Now l20n is also deprecated, the succeeded localization system  [Project Fluent](https://projectfluent.org/) is never used in B2G OS.

## KaiOS

[KaiOS](https://developer.kaiostech.com/) still uses `l10n.js` as its localization lib.

## Quick Start

Here’s a quick way to get a multilingual HTML page:

- index.html - need these metas and link to properties file
```html
<head>
  <meta name="defaultLanguage" content="en-US" />
  <meta name="availableLanguages" content="en-US, zh-CN" />
  <link rel="localization" href="./locales/sample.{locale}.properties" />
  <script defer src="./l10n.js"></script>
</head>
<body>
  <button data-l10n-id="test" title="click me!"></button>
</body>
```

- sample.{locale}.properties - key value pair
```properties
test = test button
```

It will get values for each 'data-l10n-id' and fill the translation to element's textContent. Use code below in browser console to switch language and check if it's successfully translated.
```
navigator.mozL10n.language.code = 'en-US'; // 'zh-CN'
```

The `sample/` demo works <b>on Firefox, not Chrome.</b>

Check [App localization code best practices](https://developer.mozilla.org/en-US/docs/Archive/B2G_OS/Firefox_OS_apps/Localization/Localization_code_best_practices) at MDN for l10n best practices.
