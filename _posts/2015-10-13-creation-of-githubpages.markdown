---
layout: post
title:  "Create Code Gaucho's github pages with Jekyll"
date:   2015-10-13 14:07:15
categories: jekyll github pages
---
While I'm not a blogger, we thought it would be useful to have a place where we could have a running narrative of our CodeGaucho projects.  The obvious first step is to have a blog (duh).  We had messed with [blogger] with our [codegaucho blog] and nothing wrong with that.  If I were a real blogger, blogger would be a decent platform - but we are just looking to serve up some pages.  However, as we are already github users, utilizing github pages with Jekyll seemed to be worth a shot.

Turns out to be silly easy, and direction can be found on several sites such as [How I Built this Blog] and github's own [Using Jekyll with pages].

Rather than using the default css, I loaded bootstrap 4.0 alpha from maxcdn in /_includes/head.html  Then I updated all the templates to use the bootstrap styling. 

The last step was assigning a custom domain name.  This is well documented in [github pages custom domain].  The github pages url for this site is http://codegaucho.github.io/, will probably make the custom url is http://jekyll.codegaucho.com/ (or maybe I won't)


[blogger]:         http://www.blogger.com
[codegaucho blog]: http://blogger.codegaucho.com/
[codegaucho gitpages blog]: http://codegaucho.github.io/
[Using Jekyll with pages]: https://help.github.com/articles/using-jekyll-with-pages/
[How I Built this Blog]: http://mekhami.com/jekyll/pages/github/blog/2015/07/10/How-I-Built-This-Blog.html
[github pages custom domain]: https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/

