---
layout: post
title:  "DeanLab.com - Adding Cloudinary Support"
date:   2015-10-17 16:11:15
categories: jekyll cloudinary
---

In the last post we added custom collections.  Now in these collections we want to display images

In the front matter of the document we allow the user to specify the image one of two ways:

- imageurl - the full url of any image
- imageid: v1381379684/ecibwsnz20ljfshmscy5 the cloudinary image id if we are serving this image from cloudinary (prefered)

In the index we want to display a thumbnail of the image, while in the document fully opened, we want to use a large size image. To handle this, we use [cloudinary].

We love cloudinary. Upload a full size image, and as you need smaller sizes or other special effects, just pass some options in the image url and it will build these images dynamically. These new sizes are then stored on a cdn so it gets served up nice and fast.

We want to provide sensible defaults for presenting these images, while at the same time allowing the user to over-ride these defaults where needed

To the config we add a couple of things to allow this to work for our research collection

{% highlight bash %}
cloudinary_id: codegaucho

collections:
  research:
    output: true

defaults:
  -
    scope:
      type: research
    values:
      image_options: "c_scale,w_320"
      thumbnail_options: "c_scale,w_256"
{% endhighlight %}

Note, Jekyll's documentation shows the use of "collection: research" in the scope.  However, in use we found that it applied the defaults to all collections. By using "type: research" we were able to focus the defaults to the appropriate collection.

In our layout, we can now buid the url for the properly sized (and styled, if desired) image as follows

{% highlight bash %}
{% raw %}
{% if page.imageid %}
  {% capture imageurl %}http://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/{{page.image_options}}/{{page.imageid}}{% endcapture %}
{% elsif page.imageurl %}
  {% capture imageurl %}{{page.imageurl}}{% endcapture %}
{% endif %}
{% endraw %}
{% endhighlight %}

The frontmatter of a paricular research document can become
{% highlight bash %}
---
layout: research
title: "Dynamic bandgap engineering in bilayer materials"
date:   2015-10-17 09:53:14
categories: bilayer graphene
imageid: v1381379821/ilhuewxkanxvlfkcyfiz
image_options: "c_scale,w_640"
thumbnail_options: "c_scale,w_64"
---
{% endhighlight %}

if we want to change from the default image size to 640px wide, with a 64 px wide thumbnail. For a typical post not using the defaults, we do not include image_options nor thumbnail_options

[cloudinary]:		http://cloudinary.com/
[deanlab.com]:         	http://www.deanlab.com/
