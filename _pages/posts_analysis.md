---
layout: default
permalink: /posts/story-analysis/
title:
---

<cat-nav>
  <a href="{{ site.baseurl }}/posts/all">All</a>
  <a href="{{ site.baseurl }}/posts/story-fundamentals">Story Fundamentals</a>
  <a style="color:#263573" href="{{ site.baseurl }}/posts/story-analysis">Story Analysis</a>
  <a href="{{ site.baseurl }}/posts/stories-we-live-by">Stories We Live By</a>
</cat-nav>

<hr>

<div class="posts">
  {% for post in site.categories['Story Analysis'] %}
    <article class="post">
      <h1>
          <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
      </h1>
      <div>
        <p class="post_date">{{ post.date | date: "%B %e, %Y" }}</p>
        <div class="post-tags">
          {% if post %}
            {% assign categories = post.categories %}
          {% else %}
            {% assign categories = page.categories %}
          {% endif %}
          {% for category in categories %}
            <a>{{category}}</a>
            {% unless forloop.last %}&nbsp;{% endunless %}
          {% endfor %}
        </div>
      </div>
      <div class="entry">
        {{ post.excerpt }}
      </div>
      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">
          Read More
      </a>
    </article>
  {% endfor %}
</div>