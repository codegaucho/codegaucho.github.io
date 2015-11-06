---
layout: post
title:  "Pidley.com: adding a custom domain"
date:   2015-11-01 11:11:15
categories: jekyll pidley hover
---

Bob has setup [github pages] with [jekyll] to document his site.  Will be working on the content in the coming weeks.  However, Bob wants his custom domain (pidley.com) to point to these new pages.  How to do this?

We are using [Hover] to manage all of our domains, including pidley.com.  Hover offers some nice tools to manage our domains, dns, and forwardings.

# Option 1:  Forward the site:

![Hover Forward the Domain](http://res.cloudinary.com/codegaucho/image/upload/v1446425872/pidley_forward_dnglm0.jpg)

This is the easiest - we simply put in where we want to forward the domain pidley.com to  - in this case pidley.github.com.  Not bad, but when you type in http://pidley.com, the address bar changes to http://pidley.github.io- and we were hoping to have the url be in the piley.com format.

# Option 2:  Forward the site with stealth options

![Hover Forward the Domain with Stealth](http://res.cloudinary.com/codegaucho/image/upload/v1446426650/pidley_forward_stealth_cfo31i.jpg)

A refinement of the above.  With this, the address bar will read pidley.com, which we wanted, but the address is pidley.com for every page - not what we wanted.

# Option 3: Create a subdomain that maps to our jekyll site

![Hover Forward Subdomain](http://res.cloudinary.com/codegaucho/image/upload/v1446427739/pidley_forward_subdomain_zdgfbf.jpg)

More grainular than forwarding the entire domain, we can forward only a subdomain.  Downside to this is the same as forwarding the entire domain.  Might be a good option in the future once pidley is fleshed out and has other places to go, but right now we want to keep the address at pidley.com

# Option 4: Custom subDomain with github pages

A bit less straightforward. The instructions get a bit confusing.

We initially wanted the naked domain to point to these github pages, but the recommendation is to use a subdomain.  We will do a subdomain for now and do a simple forward to this subdomain so that our root naked domain shows up at the right place. Perhaps later we will try out the naked domain.

First part is to add a CNAME record to our repository.  We created a CNAME for jekyll.pidley.com to our repository following the instructions found in [Adding a CNAME file to repository]

Then back to Hover, and we go to the DNS section and add a CNAME for our subdomain jekyll to point it at pidley.github.io

![Hover create subdomain](http://res.cloudinary.com/codegaucho/image/upload/v1446432680/pidleyCNAME2_i63ujn.png)

This works very nicely.  Our github pages are served with addresses that look like http://jekyll.pidley.com/about/ 

We then did a domain redirect (essentially option #1, but the naked domain to jekyll.pidley.com.  This pretty much gives us what we need for now

# Option 5: Custom apex domain

this option is not recommended by github.  Will give it a chance anyhow, and report on this soon.

 



[jekyll]:		http://jekyllrb.com/
[github pages]:	https://pages.github.com/
[Hover]:        https://www.hover.com 
[Setting up a custom domain with GitHub Pages]: https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/
[Adding a CNAME file to repository]: https://help.github.com/articles/adding-a-cname-file-to-your-repository/
[deanlab.com]:         	http://www.deanlab.com
[markdown]: 		http://daringfireball.net/projects/markdown/
[codegaucho blog]: 	http://blogger.codegaucho.com/
[Using Jekyll with pages]: https://help.github.com/articles/using-jekyll-
