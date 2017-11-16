---
title: ShadowDom
date: 2015-11-21 05:00:00
categories: Programming
---
<meta name="robots" content="noindex" />
<!--This page used to be a blog post, but I found that it was updated way too frequently to count as a real blog post. One reason I changed it is
I want to be able to change the dates and republish the post as an updated post for rss. The other reason is, a post is meant to be read once, or at
least a few times. Sure that is not always true and maybe someone really loves a post or needs information from it, but typically, a post is read once,
pages are read multiple times and are updated on a consistent basis. Now, the reason I left the front matter for the post intact is solely for archival
reasons. The date has no reflection on when the post was last updated. This specific post though, I will probably keep in the sitedata for programmars to
find and use. Well, I hope you enjoy my programming post (now as a page)-->

## Welcome to my Debug Page

Hello, this is my first programming post. This is more of a debug page than a post, but if you want to see it, here it is. As you may have noticed, there are weird and seemingly random scripts below. If you look at the code using either [view-source][view-source] or [viewing this post on Github][github], then you will notice that there are custom html elements below.

<show-more name="Custom HTML Demo and Code">

{% highlight html %}
<show-more name="Show More...">
I am hidden text!
</show-more>
{% endhighlight %}
will produce

<show-more name="Show More...">
I am hidden text!
</show-more>

{% highlight html %}
<markdown-parser>
**Bold**
</markdown-parser>
{% endhighlight %}
will produce

<markdown-parser>
**Bold**
</markdown-parser>

and

{% highlight html %}
<show-dropdown name="Mr. Dropdown">
<h3 class="inline">Normal Links</h3>
<a href="https://google.com/" target="_blank" class="btn btn-google"><span class="icon"></span>Google</a>
<a href="https://facebook.com/" target="_blank" class="btn btn-facebook"><span class="icon"></span>Facebook</a>
<a href="/todo.html" class="btn btn-github">Features Being Worked On</a>
<br>
<h3 class="inline">Javascript Links</h3>
<a href="/repositories.html" onclick="javascript:printable();return false;" class="btn btn-github">Printable Version</a>
</show-dropdown>
{% endhighlight %}

will produce

<show-dropdown name="Mr. Dropdown">
<h3 class="inline">Normal Links</h3>
<a href="https://google.com/" target="_blank" class="btn btn-google"><span class="icon"></span>Google</a>
<a href="https://facebook.com/" target="_blank" class="btn btn-facebook"><span class="icon"></span>Facebook</a>
<a href="/todo.html" class="btn btn-github">Features Being Worked On</a>
<br>
<h3 class="inline">Javascript Links</h3>
<a href="/repositories.html" onclick="javascript:printable();return false;" class="btn btn-github">Printable Version</a>
</show-dropdown>

<br>

Two things you may have noticed about the above example is that by default the dropdown is next to the the previous element and that just like the more element (or tag), it also uses css from external sources which influence it greatly. It will also stay inline with the element after it just as well as the element before it.

<markdown-parser>
The code that tells how these tags work are [show-more][more] and [markdown-parser][markdown]. To find the list that contains all the currently used custom tags, you can go to the [ShadowDom list][shadowdom].

[shadowdom]: {{site.github.repository_url}}/blob/{{page.branch}}/sitedata/shadowdom.html
[more]: {{site.github.repository_url}}/blob/{{page.branch}}/sitedata/customizations/more.html
[markdown]: {{site.github.repository_url}}/blob/{{page.branch}}/sitedata/customizations/markdown.html
</markdown-parser>
</show-more>

<show-more name="Shadow Explanation...">

The ShadowDom is essentially the code behind html tags. Browser vendors tend to use the ShadowDom to make otherwise complicated html such as a video player much easier.

Now, as this is a debug page and not a tutorial on ShadowDom itself I will link some other sites that explain how ShadowDom works and how to use it.

<markdown-parser>
* Links
    * [ShadowDom Explanation][shadowexplanation] - This explains what ShadowDom is.
    * [Polymer Tutorial][polymer] - This explains how to use ShadowDom.

[shadowexplanation]: http://www.html5rocks.com/en/tutorials/webcomponents/shadowdom/
[polymer]: https://www.polymer-project.org/1.0/docs/start/quick-tour.html

</markdown-parser>
</show-more>

<show-more name="Math Equations in Client-Side Markdown and HTML">
<p>This is a math equation using normal html under a custom tag: </p>
$$ \lim_{x \to c^+} f(x) = \left\{\begin{array}{ll} 3 & x \le c\\ 4x^2+5 & x > c \end{array} \right. $$
<markdown-parser>
This is a math equation written using the &lt;markdown-parser&gt; tag: 
$$ \lim_{x \to c^+} f(x) = \left\{\begin{array}{ll} 3 & x \le c\\ 4x^2+5 & x > c \end{array} \right. $$
</markdown-parser>
</show-more>

<show-more name="Downsides"><markdown-parser>
This custom tag stuff does have downsides though. Which is sad. However, they are not too major and some can be fixed by someone like me if that person can figure out how to work with it.

* MathJax does not parse the equations the same way under markdown compared to html. This results in unexpected output. The reason for this is probably because MathJax does not know how to work with the ShadowDom. In order to fix this, someone either has to force MathJax to work under the ShadowDom, probably super hard, or to rewrite the output of the LightDom source code in a way where MathJax does not see the markdown, but only sees html.
* Because the LightDom shows markdown when using &lt;markdown-parser&gt;, the highlight this page link in the footer sees the markdown and not the html output the users see.
</markdown-parser></show-more>
[view-source]: view-source:.
[github]: {{site.github.repository_url}}/blob/{{page.branch}}/{{page.path}}
