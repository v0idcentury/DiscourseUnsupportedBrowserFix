# DiscourseUnsupportedBrowserFix
All platform FIXES for (Community Platform) Discourse's Unsupported Browser issue. Tempermonkey, Chrome Extension, Mozilla Firefox, Safari and Javascript Bookmarklet.


### Tempermonkey/Violentmonkey

```
// ==UserScript==
// @name         Discourse Unsupported Browser Fix
// @namespace    DUBF1
// @version      1.0
// @description  Discourse Unsupported Browser Fix.
// @author       https://github.com/v0idcentury
// @include      *community*
// @include      *forum*
// @include      *discussion*
// @grant        none
// @run-at       document-start
// ==/UserScript==

(function() {
    // Runs before any other script on the page.
    Object.defineProperty(window, 'unsupportedBrowser', {
        // Prevent any attempt to set this property to true.
        set: function() {},
        // Report 'false' when this property is read.
get: function() { return false; },
        // Prevent the website from tampering.
        configurable: false
    });
})();
```

Note: For new websites, add an unique phrase from their URL after "@include".
