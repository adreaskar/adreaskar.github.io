---
layout: archive
title: "Sitemap"
excerpt: "The sitemap of the website"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

A list of all the posts and pages found on the site. For you robots out there is an [XML version]({{ base_path }}/sitemap.xml) available for digesting as well.

<h2>Pages</h2>
{% for post in site.pages %}
{% unless post.title == "Archive Layout with Content" or post.title == "Posts by Category" or post.title == "Posts by Collection" or post.title == "Markdown" or post.title == "Page Archive" or post.title == "Portfolio" or post.title == "Sitemap" or post.title == "Posts by Tags" or post.title == "Talk map" or post.title == "Teaching" or post.title == "Terms and Privacy Policy" or post.title == "Blog posts" or post.title == "Jupyter notebook markdown generator" %}
  {% include archive-single.html %}
{% endunless %}
{% endfor %}

<!-- <h2>Posts</h2>
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %} -->

<hr>

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" or collection.label == "portfolio" or collection.label == "teaching" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label and label == "publications" %}
  <h2>Publications</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
  {% if label != written_label and label == "talks" %}
  <hr>
  <h2>Talks</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" or collection.label == "portfolio" or collection.label == "teaching" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}
