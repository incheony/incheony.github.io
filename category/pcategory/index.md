---
layout: page
title: Project Categories
comments: false
---

{% capture site_pcategory %}{% for tag in site.pcategory %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign category_list = site_pcategory | split:',' | sort %}

<ul class="entry-meta inline-list">
  {% for item in (0..site.pcategory.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ pcategory_list[item] | strip_newlines }}{% endcapture %}
  	<li><a href="#{{ this_word }}" class="tag"><span class="term">{{ this_word }}</span> <span class="count">{{ site.pcategory[this_word].size }}</span></a></li>
  {% endunless %}{% endfor %}
</ul>

<br>

<hr class="hr-line">

<br>
<br>

{% for item in (0..site.pcategory.size) %}{% unless forloop.last %}
  {% capture this_word %}{{ pcategory_list[item] | strip_newlines }}{% endcapture %}
	<article>
	<h2 id="{{ this_word }}" class="tag-heading">{{ this_word }}</h2>
		<ul>
    {% for post in site.pcategory[this_word] %}{% if post.title != null %}
      <li class="entry-title"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endif %}{% endfor %}<br>
		</ul>
	</article><!-- /.hentry -->
{% endunless %}{% endfor %}
