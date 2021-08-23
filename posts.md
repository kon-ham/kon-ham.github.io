---
layout: page
title: Posts (By Category)
---

{% assign sorted_cats = site.categories | sort %}
{% for category in sorted_cats %}
{% assign sorted_posts = category[1] | reverse %}
<h2 id="{{category[0] | uri_escape | downcase }}">{{ category[0] }}</h2>
  <ul>
    {% for post in sorted_posts %}
    <li><a href="{{ site.url }}{{ site.baseurl }}{{  post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}