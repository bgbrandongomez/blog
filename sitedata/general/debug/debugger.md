---
layout: default
title: Ajax Debugger
project: Ajax Debugger
description: This is the page I will use to debug my Ajax Requests with the Github API.
---
<meta name="robots" content="noindex" />
<script src="/sitedata/javascripts/github/ajax-api.js"></script>
<script>
function auth() {
  $(document).ready(function() {
    username = $("#username").val();
    password = $("#password").val();
    url = $("#url").val();
    data = $("#data").val();
    method = $("#method option:selected").val(); //This allows me to set the method using a form, otherwise I would just create a function and set it directly.
    if($('#savepw').prop('checked')) {
      $('#login').submit(); //Prompts Save Password (only works in Firefox, causes a refresh in Chrome)
    }
  });
}
function table(json) {
  $(document).ready(function() {
    $('.index-table').remove();
    $('.item-table').remove();
    jQuery.each(json, function(index, item) {
        if(item instanceof Object) {
          recurseTable(index, item);
        } else {
          $('#ajax-table-body').append("<tr><td class=\"index-table\" style=\"text-align: left\">" + index + "</td>" + 
          "<td class=\"item-table\" style=\"text-align: left\">" + item + "</td></tr>");
        }
    });
  });
}

//Document Necessary Functions

$(document).ready(function() {
  $('#authenticate').click(function() {
    auth();
    var rawJSON = lookup();
    raw(rawJSON);
    table($.parseJSON(rawJSON));
  });
  $('#setCookie').click(function() {
    document.cookie = $("#cookie").val();
  });
  $('#readAllCookie').click(function() {
    $("#cookie").val(document.cookie);
  });
});
function raw(json) {
  $(document).ready(function() {
    $("#ajax-output-debug").text(json);
  });
}
function recurseTable(key, value) {
  $(document).ready(function() {
    if(value instanceof Object) {
      $.each(value, function(k, v) {
        if(v instanceof Object) {
          recurseTable(k, v);
        } else {
          $('#ajax-table-body').append("<tr><td class=\"index-table\" style=\"text-align: left\">" + key + " --> " + k + "</td>" + 
          "<td class=\"item-table\" style=\"text-align: left\">" + v + "</td></tr>");
        }
      });
    }
  });
}
</script>

<form id="login">
Username: <input type="text" id="username">
Password: <input type="password" id="password"><br>

<input id="savepw" type="checkbox" name="savepw"> Save Password (Firefox Only)<br>

URL: <input type="text" id="url" value="https://api.github.com/user">
Data: <input type="text" id="data" value="{}"><br>

Method: 
<select id="method">
  <option value="GET">Get</option>
  <option value="POST">Post</option>
  <option value="HEAD">Head</option>
  <option value="DELETE">Delete</option>
  <option value="PUT">Put</option>
</select><br>

Cookies:
Data <input type="text" id="cookie" value="access_token=XXXXXXXXXX">
<a id="setCookie" href="#">Set</a>
<a id="readAllCookie" href="#">Read All</a>
<a id="authenticate" href="#" style="float: right;">Submit</a>
</form>

<br>

### Ajax Output
<pre id="ajax-output-debug"><div class="highlight" style="color:#b5e853">Output Not Generated...</div></pre>

<br>

<table>
  <thead>
    <tr>
      <th style="text-align: left">Index</th>
      <th style="text-align: left">Item</th>
    </tr>
  </thead>
  <tbody id="ajax-table-body">
    <tr>
      <td class="index-table" style="text-align: left">Output Not Generated...</td>
      <td class="item-table" style="text-align: left">Output Not Generated...</td>
    </tr>
  </tbody>
</table>

### Pages Which Are Important
* [Javascript Ajax Requests][js-ajax]
* [Github API Version 3][github-api]
* [Authentication Script][script]

### Live HTTP Headers
* [Chrome][chrome-headers]
* [Firefox][firefox-headers]

[js-ajax]: http://stackoverflow.com/questions/25515936/perform-curl-request-in-javascript
[github-api]: https://developer.github.com/v3/
[script]: https://github.com/SenorContento/SenorContento.github.io/blob/master/sitedata/javascripts/github/ajax-api.js
[chrome-headers]: https://chrome.google.com/webstore/detail/live-http-headers/iaiioopjkcekapmldfgbebdclcnpgnlo
[firefox-headers]: https://addons.mozilla.org/en-us/firefox/addon/live-http-headers/
