---
layout: post
title:  "Site Search with FreeFind"
date:   2015-11-14 11:11:15
categories: jekyll codegaucho search
---

For most of our sites, we are going to want some sort of site search.  There are a good few ways to handle this, here we are going to show how to use [freefind] to provide this service.

First off, register your site with [freefind].  FreeFind provides some HTML and js snippets to do a dynamic modal based on search.  We used this as a starting point, but the style doesn't match bootstrap, so we had to make a couple of changes.

In the navigator we can create a search input and button 

{% highlight bash %}
{% raw %}
{% if site.freefind %}
      <form id="ffresult_sbox1" class="form-inline navbar-form pull-right" method="get" action="http://search.freefind.com/find.html" onsubmit="ffresults.show(1);">
        <input type="hidden" name="si" value="{{site.freefind}}">
		<input type="hidden" name="pid" value="r">
		<input type="hidden" name="n" value="0">
		<input type="hidden" name="_charset_" value="">
		<input type="hidden" name="bcd" value="&#247;">
		<input type="hidden" name="sbv" value="j1">
   
        <div class="input-group">
          <input class="form-control" type="text" name="query" placeholder="Search">
            <span class="input-group-btn">
                <button class="btn btn-primary" type="submit">
                    <i class="fa fa-search"></i>
                </button>
            </span>
        </div>
      </form>
      {% endif %}
{% endraw %}
{% endhighlight %}

In the _config.yml, we add the freefind site id.

Then we need to create a modal
{% highlight bash %}
{% raw %}
<div class="modal fade bd-example-modal-lg" tabindex="-1" role="dialog" aria-labelledby="myLargeModalLabel" aria-hidden="true" id="searchResultsModal">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">

      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
          <span class="sr-only">Close</span>
        </button>
        <h4 class="modal-title" id="myModalLabel">Search Results</h4>
      </div>

      <div class="modal-body">
	    <iframe  id="ffresult_ifr" name="ffresult_frame"  scrolling="auto" frameborder="0" width="100%" height="395px"></iframe>
	  </div>

      <div class="modal-footer">
        search results from <a href="http://freefind.com">FreeFind</a>
      </div>
    </div>
  </div>
</div>
{% endraw %}
{% endhighlight %}

And finally, in the freefind javascript we need to open up the modal by adding 

$('#searchResultsModal').modal('show');

as the last line of the show method.  Much of the code in the FreeFind javascript is no longer needed once you rely on the bootstrap modal.  Fhe full example can be found in the [deanlab github repo]]


[freefind]:      http://freefind.com
[deanlab github repo]: https://github.com/deanlab/deanlab.github.io
