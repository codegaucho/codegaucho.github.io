---
layout: page
title: Portfolio
date:   2015-10-29 09:53:14
permalink: /portfolio/
active_nav: Portfolio
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

  {% cycle '', '', '', '</div><div class="row">' %}
  <div class="col-md-4 portfolio-item">
    <a href="#">
      <img class="img-responsive" src="{{ imageurl }}" alt="">
    </a>
    <h3>
      <a href="#">Project Name</a>
    </h3>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam viverra euismod odio, gravida pellentesque urna varius vitae.</p>
  </div>
{% endfor %}

{% raw %}
  </div>
</div>
{% endraw %}

