---
layout: post
title: iPhone 6 and 6 Plus sizes
---

{{ page.title }}
================
Starting work on the iPhone 6 and iPhone 6 plus.
I am working on a hybrid app. A native wrapper and a UIWebView with my main code in HTML/JS/CSS.
But for this testing I am simply doing a mobile safari home-screen bookmark.

iPhone 6 Plus in portrait from the web context in JavaScript:
  window.screen.width === 414;
  window.screen.height === 736;
  window.innerWidth === 414;
  window.innerHeight === 716;
  
iPhone 6 Plus in landscape from the web context in JavaScript:
  window.screen.width === 414;
  window.screen.height === 736;
  window.innerWidth === 736;
  window.innerHeight === 414;
  
A few things are interesting here:

1) The window.screen.width / height stay the same. The iPhone 6 Plus
2) In landscape the web app goes full screen, with no status bar.


