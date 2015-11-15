---
title: Jekyll Capitalize Categories
layout: post
category: Learning
---
I just wasted two hours solving a problem caused by throwing away good information.

Jekyll has a `site.categories` collection that keeps a list of all categories on
a site. As it should. For some crazy reason, though, that list throws away case
formatting. For example, a category called "My Category" would be stored as "my
category" in `site.categories`.

I iterate over `site.categories` to build my navigation menu, so I wanted that
case-sensitivity back. I found a hack that works. Keep reading to see my solution.

<!-- more -->

Note: There is almost certainly a clean fix by adding plugins, but I am using
GitHub Pages for my site, and do not control the Jekyll configuration.

### The Problem

{% highlight html %}
{% raw %}
<ul>
{% for category in site.categories %}
  <li>
    <a href="/{{ category | first }}.html">{{ category | first | capitalize }}</a>
  </li>
{% endfor %}
</ul>
{% endraw %}
{% endhighlight %}

This would create a series of links for category pages. Where the first piece of
information stored in a category is its name. So in the case of `site.categories`
containing the following: `['cat1', 'cat2']` Jekyll would produce:

{% highlight html %}
<ul>
  <li>
    <a href="/cat1.html">Cat1</a>
  </li>
  <li>
    <a href="/cat2.html">Cat2</a>
  </li>
</ul>
{% endhighlight %}

But let's use a real-world example and see where this falls apart. Assume we have
the categories "Reading List" and "My Thoughts". Here, `site.categories` contains:
`['reading list', 'my thoughts']`. Note the stripped case.

Our code above would produce:

{% highlight html %}
<ul>
  <li>
    <a href="/reading list.html">Reading list</a>
  </li>
  <li>
    <a href="/my thoughts.html">My thoughts</a>
  </li>
</ul>
{% endhighlight %}

So note here: the `capitalize` filter only capitalizes the first character of the
filtered string (not all words.) I could find no combination of filters that gave
me the title-case, camel-case or otherwise solution that I wanted.

Note also: [the space in the URL is debatably okay.](https://talk.jekyllrb.com/t/category-with-2-words-url-problems/598)

### The Hacky Solution

So I'll cut to the chase. I said I found a solution. On the individual `post`
object inside the `site.categories.CATEGORY` collection, there is a variable
exposed called `category` if you use a single category per post.

So basically, if your YAML FrontMatter looks like:

{% highlight yaml %}
---
title: Jekyll Capitalize Categories
layout: post
category: Jekyll Issues
---
{% endhighlight %}

Then the `post` or `page` element viewing this post will have a `post.category`
element that has "Jekyll Issues" with correct capitalization.

In my case, I *only* use the single `category:` FrontMatter, not the plural. So
all my posts have a `post.category`.

Ergo:

{% highlight html %}
{% raw %}
<ul>
{% for category in site.categories %}
  <li>
    <a href="/{{ category | first }}.html">{{ category[1][0].category }}</a>
  </li>
{% endfor %}
</ul>
{% endraw %}
{% endhighlight %}

Produces:

{% highlight html %}
<ul>
  <li>
    <a href="/jekyll issues.html">Jekyll Issues</a>
  </li>
</ul>
{% endhighlight %}

Note the two different capitalizations. In the `category` object here, `category[0]`
is the mangled name (eg- 'jekyll issues'), `category[1]` is the list of posts in
that category. Therefore `category[1][0]` is the first `post` in a category.

And since each `post` in my system has a `post.category` defined by the YAML
FrontMatter: `category[1][0].category` retrieves the non-mangled category name
from the first post in that category (eg- 'Jekyll Issues').

### TL;DR

To display the Jekyll category name preserving case (eg- Title Case or whatever):

{% highlight javascript %}
{% raw %}
{% for category in site.categories %}
  {{ category[1][0].category }}
{% endfor %}
{% endraw %}
{% endhighlight %}

Note: This only works when you use `category:` in the YAML FrontMatter. If you
use `categories:` to apply several categories to a post, you're on your own.
[Good luck.](http://jekyllrb.com/docs/plugins/)
