---
layout: archive
title: "Publications"
excerpt: "My published research papers"
permalink: /publications/
author_profile: true
---

You can also find my articles on <a href="https://scholar.google.com/citations?user=cRMQ4SAAAAAJ&hl=en&authuser=1">my Google Scholar profile</a>.

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
