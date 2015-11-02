---
layout: page
title: Projects
permalink: /projects/
active_nav: Projects
---

Here are a few of the projects that we have recently worked on here at CodeGaucho.

{% raw %}
<div class="container">
  <div class="row">
{% endraw %}

{% for page in site.projects %}
  {% if page.imageid %}
    {% capture imageurl %}http://res.cloudinary.com/{{site.cloudinary_id}}/image/upload/{{page.thumbnail_options}}/{{page.imageid}}{% endcapture %}
  {% elsif page.image_url %}
    {% capture imageurl %}{{page.imageurl}}{% endcapture %}
  {% endif %}

  {% cycle '', '', '', '', '</div><div class="row">' %}
  <div class="col-lg-3">
    <div class="card">
      <img alt="100%x200" class="card-img-top img-responsive" style="display: block;" src="{{ imageurl }}">
      <div class="card-block">

      <h3 class="card-title"><a href="{{ equip.url | prepend: site.baseurl }}">{{ page.title }}</a></h3>
      <p class="card-text">{{ page.description }}</p>
      <p class="card-text"><small class="text-muted"><a href="{{ page.url | prepend: site.baseurl }}">More...</a></small></p>
    </div>
  </div>
</div>
{% endfor %}

{% raw %}
  </div>
</div>
{% endraw %}

