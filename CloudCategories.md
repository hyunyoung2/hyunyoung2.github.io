---
layout: page
title: Study List With Categories
subtitle: Something that I have studied and experienced
css: "/css/CloudListFilter.css"
bigimg: 
  - "/img/Image/BigImages/carmel.jpg" : "Carmel-by-the-Sea, CA (2016)"
  - "/img/Image/BigImages/monterey.jpg" : "Monterey, CA (2016)"
  - "/img/Image/BigImages/stanford_dish.jpg" : "Stanford Dish, CA (2016)"
  - "/img/Image/BigImages/marian_beach_in_sanfran.jpg" : "MRINA of San Francisco, CA (2016)"
  - "/img/Image/BigImages/carmel2.jpg" : "Carmel-by-the-Sea, CA (2016)"
  - "/img/Image/BigImages/marina.jpg" : "MRINA of San Francisco, CA (2016)"
  - "/img/Image/BigImages/sanfrancisco.jpg" : "San Francisco, CA (2016)"
---

{: #top }

{% include CloudHeaderPart.html %}

<!-- this code si from https://github.com/daattali/daattali.github.io/blob/master/index.html --> 
<div class="list-filters post-preview">
  <a href="/" class="list-filter">All posts</a>
  <a href="/CloudCategories" class="list-filter filter-selected">Catergories Cloud</a>
  <a href="/CloudTags" class="list-filter">Tags Cloud</a>
  <a href="/CloudDate" class="list-filter">List by Date</a>
</div>


<!-- I follow the file from cloudoftags file of my github(https://github.com/hyunyoung2/hyunyoung2.github.io/blob/master/cloudoftags.html)-->

<!-- this code from https://github.com/codinfox/codinfox-lanyon/blob/dev/blog/categories.html-->
  <div class="blog-tags"> 
    {% assign tags = site.categories | sort %}
    {% for tag in tags %}
    <a href="#{{ tag[0] | slugify }}" class="btn btn-default" style="font-size: {{ tag | last | size  |  times: 4 | plus: 80  }}%"> <!-- style="color: #1C1C1C;" is font color of cloud index -->
      <span class="fa fa-folder-open" aria-hidden="true" style="color: #1C1C1C;"> <!-- I get rid of left option -->
        {{ tag[0] }} <i class="badge">{{ tag | last | size }}</i>
      </span>
    </a>
    {% endfor %}
  </div>
  <hr/> <!-- margin-top and margin-bottom in main.css -->
  <div class="post-preview"> <!--post-preview -->
    {% for tag in tags %} <!-- style="padding-top: 70px;" is used to deal with nav-custom bar -->
      <h2 id="{{ tag[0] | slugify }}" style="padding-top: 70px;"> {{ tag[0] }}  <i class="badge">{{ tag | last | size }}</i></h2> <!-- I added new class -->
      <ul class="later on"> <!-- post-subtitle -->
        {% for post in tag[1] %}
          <a class="post-subtitle" href="{{ site.baseurl }}{{ post.url }}">
        <li>
          {{ post.title }}
        <small class="post-meta"> - Posted on {{ post.date | date: "%B %-d, %Y" }}</small>
        </li>
        </a>
        {% endfor %}
      </ul>
        <a href="#top" class="btn btn-default" style="font-size: 15px; padding: 0px 5px; margin-left: 30px">
          <span class="fa fa-refresh" aria-hidden="true"></span> Go back to the top
        </a> 
        <hr/>
    {% endfor %}
  </div>
