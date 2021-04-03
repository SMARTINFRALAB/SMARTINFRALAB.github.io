---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

See <a href="{{site.author.googlescholar}}">Google Scholar</a> for a full list of publications.

{% include base_path %}

## Preprints and working papers

<ol>
{% for post in site.publications reversed %}
  {% if post.type == 'preprint' %}
  <li class="publication__li"><a href="{{post.permalink}}">{{post.citation}}</a></li>
  {% endif %}
{% endfor %}
</ol>


## Journal articles

<ol>
{% for post in site.publications reversed %}
  {% if post.type == 'article' %}
  <li class="publication__li"><a href="{{post.permalink}}">{{post.citation}}</a></li>
  {% endif %}
{% endfor %}
</ol>

## Conference Proceedings

<ol>
{% for post in site.publications reversed %}
  {% if post.type == 'refereed-conference-proceeding' %}
  <li class="publication__li"><a href="{{post.permalink}}">{{post.citation}}</a></li>
  {% endif %}
{% endfor %}
</ol>

## Invited Talks

<ol>
{% for post in site.publications reversed %}
  {% if post.type == 'invited-talk' %}
  <li class="publication__li"><a href="{{post.permalink}}">{{post.citation}}</a></li>
  {% endif %}
{% endfor %}
</ol>

## Technical reports

<ol>
{% for post in site.publications reversed %}
  {% if post.type == 'tech_report' %}
  <li class="publication__li"><a href="{{post.permalink}}">{{post.citation}}</a></li>
  {% endif %}
{% endfor %}
</ol>

## Theses

<ol>
{% for post in site.publications reversed %}
  {% if post.type == 'thesis' %}
  <li class="publication__li"><a href="{{post.permalink}}">{{post.citation}}</a></li>
  {% endif %}
{% endfor %}
</ol>

