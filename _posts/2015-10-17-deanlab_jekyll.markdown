---
layout: post
title:  "DeanLab.com - Jekyll and GitHub pages for website"
date:   2015-10-17 09:11:15
categories: jekyll
---

Yes, [jekyll] is a blog aware platform, and maybe not the ideal choice for a website in many cases.  However, with this particular website ([deanlab.com]) and utilizing Jekyll's collections, it might be ideal.

* It is a slow moving website - not loads of content creation.
* Those adding the pages are tech savvy and [markdown] is ideal.
* GitHub is already in use, so this can be hosted in GitHub pages
* It will be simpler

First word of warning, in Jekyll's documentation, it is crystal clear that using collections this way could be problematic.

> Collections support is unstable and may change
> 
> This is an experimental feature and the API may change until the feature stabilizes.

Ok, good to know.  I'm going to chance it.

Following mostly along with [Using Jekyll with pages]

on GitHub:
- Create github organization for deanlab
- Create repository for deanlab.github.io

{% highlight bash %}
gem install jekyll
gem install bundler
mkdir deanlab
cd deanlab
jekyll new .
{% endhighlight %}

now create a file in this new directory named Gemfile containing
source 'https://rubygems.org'
gem 'github-pages'

{% highlight bash %}
bundle install
bundle exec jekyll serve
{% endhighlight %}

Hooray, we have a jekyll site up and running locally.  Now lets get it to github pages

{% highlight bash %}
git init
git add -A
git commit -m "jekyll initialization"
git remote add origin https://github.com/deanlab/deanlab.github.io.git
git push -u origin master
{% endhighlight %}

Now take a look at deanlab.github.io - we have a github pages website - yeah. Now time to make it our own and add the collections

[jekyll]:		http://jekyllrb.com/
[deanlab.com]:         	http://www.deanlab.com
[markdown]: 		http://daringfireball.net/projects/markdown/
[codegaucho blog]: 	http://blogger.codegaucho.com/
[Using Jekyll with pages]: https://help.github.com/articles/using-jekyll-
