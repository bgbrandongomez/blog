---
layout: default
project: Redirect Page
description: This is a page which I use to track redirects of any links that I feel like tracking
title: Redirect to Twitter
---
<meta name="robots" content="noindex" />
<!--Notice there will be a flash when switching on the text Redirecting to... when switching between pages. That is as a result of the next page not instantly displaying the redirect message, but instead choosing the wait half a second to make sure of a valid redirect. I could change this behavior, but I don't know if I want to yet-->

<link rel="shortcut icon" type="image/x-icon" href="https://www.twitter.com/favicon.ico" />

### Redirecting you to Twitter...

<script>
window.setTimeout(function(){
    window.location = "/to.html?name=Twitter";
}, 500);
</script>
<noscript markdown="1">
<meta http-equiv="refresh" content="5;URL='https://twitter.com/BrandonAndrewGo'" />
<p>Hello, it appears you do not have Javascript! I will redirect you to [https://twitter.com/BrandonAndrewGo][twitter] instead of the normal redirect, but this link may or may not be valid. Brandon may have forgotten to update this link if he changed any his social media links.</p>

[twitter]: https://twitter.com/BrandonAndrewGo
</noscript>
