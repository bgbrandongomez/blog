---
layout: default
title: Bible Verse Tester
project: Bible Verse Tester - Polymer
description: This is the page I will use to debug polymer displaying the Bible verses.
---
<meta name="robots" content="noindex, nofollow" />
### Code

{% highlight html %}
<bible-verse>Phillipians 1:21</bible-verse>
<bible-verse says="true">John 3:16</bible-verse>
<bible-verse link="true">Genesis 1</bible-verse>
<bible-verse passage="true">Genesis 1</bible-verse>
<bible-verse color="blue">Job 1:6-12</bible-verse>
<bible-verse url="internal">Songs of Solomon 2:16</bible-verse>
{% endhighlight %}

### Output

<bible-verse>Phillipians 1:21</bible-verse>

<bible-verse says="true">John 3:16</bible-verse>

<bible-verse link="true">Genesis 1</bible-verse>

<bible-verse passage="true">Genesis 1</bible-verse>

<bible-verse color="blue">Job 1:6-12</bible-verse>

<bible-verse url="internal">Songs of Solomon 2:16</bible-verse>

<hr>

## Notes

* The Bible Verse formatter will
    * display the verse inline in the same formatting as the text or paragraph it is in
    * display the verse in a code box like the one that is on Thanksgiving to The Lord
    * work on rss readers (maybe, if possible)
* It will also allow attributes such as
    * color - for inline
    * says - Verse Name says "Verse" (Version)
    * passage - for the code boxes
    * link - only display link (useful when referencing to a passage)
    * url - used to control where link goes to
        * internal - Redirect to Internal Copy of the <short-text abbr="WEB">World English Bible</short-text>
        * youversion - (default) Redirect to YouVersion so user can bookmark it for his/her Bible app
* The defaults which don't need attributes are
    * inline - verse embeded within a text 
    * nosays - Verse Name "Verse" (Version)
* The formatter should be able to handle syntax differences such as
    * Song of Solomon <short-text abbr="vs.">versus</short-text> Songs of Solomon
    * Psalms and Psalm
* The formatter will probably not use the short-text element as that would become annoying if every single verse had that

<br>

## Examples of the Bible verse output are

### Default

{% highlight html %}
<bible-verse>Romans 12:2</bible-verse>
{% endhighlight %}

<a href="https://www.bible.com/bible/206/rom.12.2.web">Romans 12:2</a> “Don’t be conformed to this world, but be transformed by the renewing of your mind, so that you may prove what is the good, well-pleasing, and perfect will of God." (WEB)

<hr>

### Says (Sentence Like)

{% highlight html %}
<bible-verse says="true">1st Chronicles 29:13</bible-verse>
{% endhighlight %}

<a href="https://www.bible.com/bible/206/1ch.29.13.web">1st Chronicles 29:13</a> says "Now therefore, our God, we thank you, and praise your glorious name." (WEB)

<hr>

### Link Only (useful in conjunction with passage)

{% highlight html %}
<bible-verse link="true">Psalms 107</bible-verse>
{% endhighlight %}

<a href="https://www.bible.com/bible/206/psa.107.web">Psalms 107</a>

<hr>

### Passage

{% highlight html %}
<bible-verse passage="true">Psalms 107</bible-verse>
{% endhighlight %}

<pre><b>Psalms 107:1-9 (WEB)</b>
<span style="color:blue">1</span> Give thanks to Yahweh, for he is good,
for his loving kindness endures forever.
<span style="color:blue">2</span> Let the redeemed by Yahweh say so,
whom he has redeemed from the hand of the adversary,
<span style="color:blue">3</span> And gathered out of the lands,
from the east and from the west,
from the north and from the south.
 
<span style="color:blue">4</span> They wandered in the wilderness in a desert way.
They found no city to live in.
<span style="color:blue">5</span> Hungry and thirsty,
their soul fainted in them.
<span style="color:blue">6</span> Then they cried to Yahweh in their trouble,
and he delivered them out of their distresses,
<span style="color:blue">7</span> he led them also by a straight way,
that they might go to a city to live in.
<span style="color:blue">8</span> Let them praise Yahweh for his loving kindness,
for his wonderful deeds to the children of men!
 
<span style="color:blue">9</span> For he satisfies the longing soul.
He fills the hungry soul with good.
</pre>

<show-more name="More Examples...">

<hr>

<h3>Color</h3>

{% highlight html %}
<bible-verse color="#b5e853;">Revelation 21:9</bible-verse>
{% endhighlight %}

<a href="https://www.bible.com/bible/206/rom.12.2.web">Revelation 21:9</a> <p style="color: #b5e853; display: inline;">"One of the seven angels who had the seven bowls, who were loaded with the seven last plagues came, and he spoke with me, saying, "Come here. I will show you the wife, the Lamb’s bride.""</p> (WEB)

<ul><li>This applies to both says and default inline statements</li></ul>

<hr>

<h3>Internal Link</h3>

{% highlight html %}
<bible-verse url="internal">1st Corinthians 15:57</bible-verse>
{% endhighlight %}

<a href="/sitedata/web/1CO15.htm#V57">1st Corinthians 15:57</a> "But thanks be to God, who gives us the victory through our Lord Jesus Christ." (WEB)

<ul><li>This applies to all statements that contain links</li></ul>
</show-more>
