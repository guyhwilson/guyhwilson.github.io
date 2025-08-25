---
layout: archive
title: "Blog"
permalink: /blog/
author_profile: false
---

<style>
.archive {
  padding-left: 0 !important;
  margin-left: 0 !important;
}
.archive .page {
  margin-left: 0 !important;
  padding-left: 0 !important;
}
.archive h2 {
  margin-left: 0 !important;
  padding-left: 0 !important;
}
.archive p {
  margin-left: 0 !important;
  padding-left: 0 !important;
}
</style>

{% for post in site.posts %}
  <article class="page" itemscope itemtype="http://schema.org/CreativeWork" style="margin-bottom: 2em;">
    <h2 itemprop="headline" style="font-weight: normal; margin-bottom: 0.2em;">
      <a href="{{ post.url | relative_url }}" rel="permalink" style="text-decoration: none;">{{ post.title }}</a>
    </h2>
    
    {% if post.date %}
      <p class="page__date" style="margin-top: 0.2em; margin-bottom: 1em;">
        <time datetime="{{ post.date | date_to_xmlschema }}" style="font-style: italic;">{{ post.date | date: "%B %d, %Y" }}</time>
      </p>
    {% endif %}
    
    {% if post.excerpt %}
      <p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | remove: '<p>' | remove: '</p>' }}</p>
    {% else %}
      <p class="archive__item-excerpt" itemprop="description">{{ post.content | truncatewords: 50 | strip_html }}</p>
    {% endif %}
  </article>
{% endfor %} 