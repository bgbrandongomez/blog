---
layout: default
project: Redirect Page
description: This is a page which I use to track redirects of any links that I feel like tracking
title: Redirect to Facebook
---
<meta name="robots" content="noindex" />
<!--Notice there will be a flash when switching on the text Redirecting to... when switching between pages. That is as a result of the next page not instantly displaying the redirect message, but instead choosing the wait half a second to make sure of a valid redirect. I could change this behavior, but I don't know if I want to yet-->

<link rel="shortcut icon" type="image/x-icon" href="https://www.facebook.com/favicon.ico" />

### Redirecting you to Facebook...

<script>
window.setTimeout(function(){
    window.location = "/to.html?name=Facebook";
}, 500);
</script>
<noscript markdown="1">
<meta http-equiv="refresh" content="5;URL='https://www.facebook.com/SenorContento'" />
<p>Hello, it appears you do not have Javascript! I will redirect you to [https://www.facebook.com/SenorContento][facebook] instead of the normal redirect, but this link may or may not be valid. Brandon may have forgotten to update this link if he changed any his social media links.</p>

[facebook]: https://www.facebook.com/SenorContento
</noscript>
