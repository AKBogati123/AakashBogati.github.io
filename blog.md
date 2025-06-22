---
layout: page
title: "Blog"
permalink: /blog/
---

<div class="blog-header">
  <h1>All Posts</h1>
  <p>Thoughts, tutorials, and insights from my development journey</p>
</div>

<div class="blog-content">
  <div class="posts-container">
    {% for post in site.posts %}
    <article class="blog-post-card">
      <div class="post-meta">
        <time class="post-date">{{ post.date | date: "%B %d, %Y" }}</time>
        {% if post.categories.size > 0 %}
        <div class="post-categories">
          {% for category in post.categories limit:3 %}
          <span class="category-tag">{{ category }}</span>
          {% endfor %}
        </div>
        {% endif %}
      </div>
      
      <h2 class="post-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      
      {% if post.excerpt %}
      <div class="post-excerpt">
        {{ post.excerpt | strip_html | truncatewords: 40 }}
      </div>
      {% endif %}
      
      <div class="post-footer">
        <a href="{{ post.url | relative_url }}" class="read-more-btn">
          Read Full Post <span>→</span>
        </a>
        <div class="post-stats">
          <span class="read-time">{{ post.content | number_of_words | divided_by: 200 }} min read</span>
          <span class="word-count">{{ post.content | number_of_words }} words</span>
        </div>
      </div>
    </article>
    {% endfor %}
  </div>
  
  {% if site.posts.size == 0 %}
  <div class="no-posts-message">
    <div class="no-posts-icon">📝</div>
    <h2>No posts yet!</h2>
    <p>I'm working on some amazing content. Check back soon for insightful posts about development, programming, and technology!</p>
  </div>
  {% endif %}
</div>
