---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

See <a href="{{site.author.googlescholar}}">Google Scholar</a> for a full list of publications.

{% include base_path %}

## Journal articles

<ol>
{% for post in site.publications reversed %}
  <li>{{post.citation}}</li>
{% endfor %}
</ol>
