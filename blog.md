---
layout: page
title: Blog
permalink: /blog/
order: 1
---

<div class="blog">

<ul class="post-list">
{% for post in site.posts %}
  <li>

    <h2>
      <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </h2>

    <p class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
    </p>

    <div class="post-entry">
      {{ post.content | strip_html | xml_escape | truncatewords: 50 }}
    <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">read&nbsp;more</a>
    </div>

  </li>
{% endfor %}
</ul>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>

</div>
