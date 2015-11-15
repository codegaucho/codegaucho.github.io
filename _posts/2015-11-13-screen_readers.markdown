---
layout: post
title:  "Don't forget screen readers"
date:   2015-11-15 11:11:15
categories: jekyll codegaucho
---

It is real easy for those of us without visual impairment to forget to add the bits and pieces needed for screen readers.  One place this is important is in our navigator.

For our deanlab navigator (deanlab is a [jekyll] based website) we use a bit of liquid magic to have the screen reader tags added to indicate the current page.

{% highlight bash %}
{% raw %}
{% if p.title == page.active_nav %}
  <span class="sr-only">(current)</span>
{% endif %}
{% endraw %}
{% endhighlight %}

and this will add the "(current)" tag to the active navigator on screen readers to help folks figure out where they are.

To see the full page, go to the [deanlab github repo] and look at the header layout.

There are many other opportunities to better support screenreaders, and using the sr-only class can be used in many ways

[jekyll]:      http://jekyllrb.com
[deanlab github repo]: https://github.com/deanlab/deanlab.github.io
