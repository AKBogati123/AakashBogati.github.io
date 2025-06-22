---
layout: page
title: Blog
permalink: /blog/
---

# 📚 All Posts

<div style="margin: 2rem 0;">
{% for post in site.posts %}
  <article style="padding: 2rem; margin-bottom: 2rem; border: 1px solid #e1e5e9; border-radius: 8px; background-color: #ffffff;">
    <header>
      <h2 style="margin-bottom: 0.5rem;">
        <a href="{{ post.url | relative_url }}" style="text-decoration: none; color: #2c3e50;">{{ post.title }}</a>
      </h2>
      <p style="color: #7f8c8d; font-size: 0.9rem; margin-bottom: 1rem;">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
        {% if post.categories.size > 0 %}
          • 
          {% for category in post.categories %}
            <span style="background-color: #e3f2fd; padding: 2px 8px; border-radius: 12px; font-size: 0.8rem;">{{ category }}</span>
          {% endfor %}
        {% endif %}
      </p>
    </header>
    
    {% if post.excerpt %}
      <div style="color: #555; line-height: 1.6; margin-bottom: 1rem;">
        {{ post.excerpt | strip_html | truncatewords: 50 }}
      </div>
    {% endif %}
    
    <footer>
      <a href="{{ post.url | relative_url }}" style="color: #3498db; text-decoration: none; font-weight: 500;">Read full post →</a>
    </footer>
  </article>
{% endfor %}
</div>

{% if site.posts.size == 0 %}
<div style="text-align: center; padding: 3rem; color: #7f8c8d;">
  <h3>No posts yet!</h3>
  <p>Check back soon for awesome content.</p>
</div>
{% endif %}
