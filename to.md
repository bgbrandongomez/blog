---
layout: default
title: Redirect Page
project: Redirect Page
description: This is a page which I use to track redirects of any links that I feel like tracking
---
<meta name="robots" content="noindex">
<h3 id="redirect-message"></h3>

<script>
window.setTimeout(function(){
    var validservice = true;
    var getStr = window.location.search.substr(1);
    var getArray = getStr.split ("&");
    var get = {};

    for (var i = 0; i < getArray.length; i++) {
        var tmpArray = getArray[i].split("=");
        get[tmpArray[0]] = tmpArray[1];
    }

    if (typeof get.name !== 'undefined') {
        var validservice = true;
        if(get.name == "YouTube") {
	    //alert("Name: " + get.name);
	    window.location = "https://www.youtube.com/channel/UCykPguamRje7THT09pNrnBA";
        }
        else if(get.name == "Facebook") {
	    window.location = "https://www.facebook.com/SenorContento";
        }
        else if(get.name == "Instagram") {
	    window.location = "https://www.instagram.com/bgbrandongomez";
        }
        else if(get.name == "Twitter") {
	    window.location = "https://twitter.com/BrandonAndrewGo";
        }
        else if(get.name == "Flickr") {
	    window.location = "https://www.flickr.com/photos/137672707@N08";
        }
        else if(get.name == "SnapChat") {
	    window.location = "https://www.snapchat.com/add/bgbrandongomez";
        }
        else if(get.name == "GooglePlus") {
	    window.location = "https://plus.google.com/105811941589453921658";
        }
        else if(get.name == "CubeTechGooglePlus") {
	    window.location = "https://plus.google.com/110788237408085427995";
        }
        else if(get.name == "FourSquare") {
	    window.location = "https://foursquare.com/brandonandrewgo";
        }
        else if(get.name == "Email") {
	    window.location = "http://www.google.com/recaptcha/mailhide/d?k=01czDj1feltC84FXrLKlc7zA==&c=6tyDH9YOYsGOjk91tKgvGu1GIu0ELxCUY4ZDd6eq-Vo=";
        }
        else if(get.name == "16PersonalitiesForm") {
	    window.location = "https://docs.google.com/forms/d/e/1FAIpQLSenpuJIub6VcqzZy6bZpTMizISYbbg78IwLVU-yMVLZh22ivw/viewform";
        }
        else {
            validservice = false;
            if (typeof get.src !== 'undefined') {
               if(get.src != window.location.href.split('?')[0] && get.src != window.location.href.split('#')[0] && get.src.trim() != '' && get.src != '.') {
                $("#redirect-message").html("Unknown Service " + get.name + "! Redirecting you to " + get.src + "...");
                window.location = get.src;
               }
            }
            else {
               $("#redirect-message").html("Unknown Service " + get.name + " and no valid redirects, so bringing you to my homepage!");
               window.location = "https://senorcontento.github.io/";
            }
        }

        if(validservice == true) {
            $("#redirect-message").html("Redirecting you to " + get.name + "...");
        }
    }
    else {
        if (typeof get.src !== 'undefined') {
            if(get.src != window.location.href.split('?')[0] && get.src != window.location.href.split('#')[0] && get.src.trim() != '' && get.src != '.') {
               if(get.src != window.location.href.split('?')[0] && get.src != window.location.href.split('#')[0] && get.src.trim() != '' && get.src != '.') {
                $("#redirect-message").html("Redirecting you to " + get.name + "...");
                window.location = get.src;
               }
            }
        }
	else {
            $("#redirect-message").html("Unknown Service " + get.name + " and no valid redirects, so bringing you to my homepage!");
            window.location = "https://senorcontento.github.io/";
	}
    }
}, 500);
</script>
<noscript markdown="1">

* Hello, this is a redirect page for the site that is listed in the url bar. May I ask that you copy it and go there directly. I would redirect you automatically, but Javascript seems to either be turned off or is non-existent.
* If you are wondering why I am using this as a redirect page instead of using a url like [http://bit.ly/senorcontento][YouTube], it is because I want to be able to track all redirects in one place instead of going and visiting many sites to see who uses my links. If the iframe in the source of this page works, I already have the tracking info, I just cannot redirect as I do not know what the page url is without scripting. If I get a separate server with my own domain name and combine it with Github pages, I won't need Javascript to redirect you and could use a meta tag like the one below or just straight up redirect you using server side scripting.

{% highlight html %}
<meta http-equiv="refresh" content="5;URL='https://SenorContento.github.io/'" />
{% endhighlight %}

[YouTube]: http://bit.ly/senorcontento

</noscript>
