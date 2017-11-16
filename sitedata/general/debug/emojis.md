---
layout: default
title: Emoji Cheat Sheet
project: Emoji Cheat Sheet
description: This is the page I will use to list emojis available in Markdown.
---
<meta name="robots" content="noindex" />
<script src="/sitedata/javascripts/github/ajax-api.js"></script>
<script>
emoji();

function emoji() {
  //auth();
  url = "https://api.github.com";
  var detectEmojiURL = $.parseJSON(lookup());
  url = detectEmojiURL.emojis_url;
  var rawJSON = lookup();
  //raw(rawJSON);
  emojiJSON($.parseJSON(rawJSON));
}
function emojiJSON(json) {
  $(document).ready(function() {
    $('.index-table').remove();
    $('.item-table').remove();

    url = "/sitedata/general/debug/banned-emojis.md";
    var lines = lookup().split("\"");
    var words = lines[1].split("\\n");

    /*var banned_words = "";
    for (var i = 3, len = words.length; i < len; i++) {
      banned_words = banned_words + words[i] + "\n";
    }*/

    jQuery.each(json, function(index, item) {
      var bademoji = false;
      for (var i = 3, len = words.length; i < len; i++) {
        //banned_words = banned_words + words[i] + "\n";
        
        if(index == words[i]) {
          //alert("Emoji Bad: " + index);
          bademoji = true;
        }
      }
      if(!bademoji) { //This line can invert the banlist to a whitelist
        //alert("Emoji Good: " + index);
        $('#ajax-table-body').append("<tr><td class=\"index-table\" style=\"text-align: left\">" + index + "</td>" + 
        "<td class=\"item-table\" style=\"text-align: left\"><img src=\"" + item + "\"></img></td></tr>");
      }
    });
  });
}
</script>

This Emoji Table currently runs unauthenticated, so you only have 60 requests per hour. Authenticated you would get 5000 requests per hour.

<table>
  <thead>
    <tr>
      <th style="text-align: left">Emoji Name</th>
      <th style="text-align: left">Emoji Picture</th>
    </tr>
  </thead>
  <tbody id="ajax-table-body">
    <tr>
    </tr>
  </tbody>
</table>
