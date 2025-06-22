---
layout: page
title: "Blog"
permalink: /blog/
---

<style>
.blog-container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 2rem;
}

.blog-header {
  text-align: center;
  padding: 3rem 0;
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
  margin: -2rem -2rem 3rem -2rem;
  border-radius: 0 0 2rem 2rem;
}

.blog-header h1 {
  font-size: 3rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 0.5rem;
}

.blog-header p {
  font-size: 1.2rem;
  color: #64748b;
  margin: 0;
}

.posts-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.blog-post-card {
  background: white;
  border-radius: 1rem;
  padding: 2rem;
  box-shadow: 0 2px 10px rgba(0,0,0,0.08);
  border: 1px solid #e2e8f0;
  transition: all 0.3s ease;
}

.blog-post-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.12);
}

.post-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
  flex-wrap: wrap;
  gap: 1rem;
}

.post-date {
  color: #64748b;
  font-size: 0.9rem;
  font-weight: 500;
  background: #f1f5f9;
  padding: 0.25rem 0.75rem;
  border-radius: 2rem;
}

.post-categories {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.category-tag {
  background: linear-gradient(135deg, #3b82f6, #1d4ed8);
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 1rem;
  font-size: 0.75rem;
  font-weight: 500;
  text-transform: capitalize;
}

.post-title {
  margin-bottom: 1rem;
}

.post-title a {
  color: #1e293b;
  text-decoration: none;
  font-size: 1.75rem;
  font-weight: 700;
  line-height: 1.3;
  display: block;
}

.post-title a:hover {
  color: #3b82f6;
  transition: color 0.2s ease;
}

.post-excerpt {
  color: #4b5563;
  line-height: 1.7;
  font-size: 1.1rem;
  margin-bottom: 1.5rem;
  text-align: left;
}

.post-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 1rem;
  border-top: 1px solid #f1f5f9;
  flex-wrap: wrap;
  gap: 1rem;
}

.read-more-btn {
  background: linear-gradient(135deg, #3b82f6, #1d4ed8);
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.2s ease;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
}

.read-more-btn:hover {
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(59, 130, 246, 0.4);
}

.post-stats {
  display: flex;
  gap: 1rem;
  color: #64748b;
  font-size: 0.9rem;
  align-items: center;
}

.post-stats span {
  background: #f8fafc;
  padding: 0.25rem 0.75rem;
  border-radius: 1rem;
  font-weight: 500;
}

.no-posts-message {
  text-align: center;
  padding: 4rem 2rem;
  background: white;
  border-radius: 1rem;
  box-shadow: 0 2px 10px rgba(0,0,0,0.05);
}

.no-posts-icon {
  font-size: 5rem;
  margin-bottom: 1rem;
}

.no-posts-message h2 {
  font-size: 2rem;
  color: #1e293b;
  margin-bottom: 1rem;
}

.no-posts-message p {
  color: #64748b;
  font-size: 1.1rem;
  max-width: 500px;
  margin: 0 auto;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .blog-container {
    padding: 0 1rem;
  }
  
  .blog-header {
    margin: -1rem -1rem 2rem -1rem;
    padding: 2rem 1rem;
  }
  
  .blog-header h1 {
    font-size: 2rem;
  }
  
  .post-title a {
    font-size: 1.5rem;
  }
  
  .blog-post-card {
    padding: 1.5rem;
  }
  
  .post-meta, .post-footer {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .post-stats {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }
}
</style>

<div class="blog-container">
  <div class="blog-header">
    <h1>📚 All Posts</h1>
    <p>Thoughts, tutorials, and insights from my development journey</p>
  </div>

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
        {{ post.excerpt | strip_html | truncatewords: 50 }}
      </div>
      {% endif %}
      
      <div class="post-footer">
        <a href="{{ post.url | relative_url }}" class="read-more-btn">
          Read Full Post <span>→</span>
        </a>
        <div class="post-stats">
          <span>📖 {{ post.content | number_of_words | divided_by: 200 }} min read</span>
          <span>📝 {{ post.content | number_of_words }} words</span>
        </div>
      </div>
    </article>
    {% endfor %}
    
    {% if site.posts.size == 0 %}
    <div class="no-posts-message">
      <div class="no-posts-icon">📝</div>
      <h2>No posts yet!</h2>
      <p>I'm working on some amazing content. Check back soon for insightful posts about development, programming, and technology!</p>
    </div>
    {% endif %}
  </div>
</div>
