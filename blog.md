---
layout: default
title: "Blog"
permalink: /blog/
---

<div class="blog-page">
  <div class="blog-header">
    <div class="container">
      <h1>📚 Technical Blog</h1>
      <p>Thoughts, tutorials, and insights from my development journey</p>
      
      <div class="blog-stats">
        <div class="stat">
          <span class="stat-number">{{ site.posts.size }}</span>
          <span class="stat-label">Posts</span>
        </div>
        <div class="stat">
          {% assign total_words = 0 %}
          {% for post in site.posts %}
            {% assign words = post.content | number_of_words %}
            {% assign total_words = total_words | plus: words %}
          {% endfor %}
          <span class="stat-number">{{ total_words | divided_by: 1000 }}k+</span>
          <span class="stat-label">Words</span>
        </div>
        <div class="stat">
          <span class="stat-number">{{ site.categories.size }}</span>
          <span class="stat-label">Categories</span>
        </div>
      </div>
    </div>
  </div>

  <div class="container">
    <!-- Category Filter -->
    {% if site.categories.size > 0 %}
    <div class="category-filter">
      <button class="filter-btn active" data-category="all">All Posts</button>
      {% for category in site.categories %}
      <button class="filter-btn" data-category="{{ category[0] | slugify }}">
        {{ category[0] }} ({{ category[1].size }})
      </button>
      {% endfor %}
    </div>
    {% endif %}

    <!-- Blog Posts -->
    <div class="posts-container">
      {% for post in site.posts %}
      <article class="blog-post-card" data-categories="{% for cat in post.categories %}{{ cat | slugify }} {% endfor %}">
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
            {% assign read_time = post.content | number_of_words | divided_by: 200 %}
            {% if read_time == 0 %}{% assign read_time = 1 %}{% endif %}
            <span>📖 {{ read_time }} min read</span>
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
</div>

<style>
.blog-page {
  padding-top: 2rem;
}

.blog-header {
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
  padding: 4rem 0;
  margin-bottom: 3rem;
  text-align: center;
  border-radius: 0 0 2rem 2rem;
}

.blog-header h1 {
  font-size: 3rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 1rem;
}

.blog-header p {
  font-size: 1.2rem;
  color: #64748b;
  margin-bottom: 2rem;
}

.blog-stats {
  display: flex;
  justify-content: center;
  gap: 3rem;
  flex-wrap: wrap;
}

.stat {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 2rem;
  font-weight: 700;
  color: #3b82f6;
}

.stat-label {
  font-size: 0.9rem;
  color: #64748b;
  font-weight: 500;
}

.category-filter {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.filter-btn {
  background: white;
  color: #64748b;
  padding: 0.75rem 1.5rem;
  border: 2px solid #e2e8f0;
  border-radius: 2rem;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
}

.filter-btn:hover,
.filter-btn.active {
  background: #3b82f6;
  color: white;
  border-color: #3b82f6;
  transform: translateY(-2px);
}

.posts-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  max-width: 900px;
  margin: 0 auto;
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
  .blog-header {
    padding: 3rem 1rem;
  }
  
  .blog-header h1 {
    font-size: 2rem;
  }
  
  .blog-stats {
    gap: 2rem;
  }
  
  .category-filter {
    flex-direction: column;
    align-items: center;
  }
  
  .posts-container {
    padding: 0 1rem;
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

<script>
// Category filtering functionality
document.addEventListener('DOMContentLoaded', function() {
  const filterBtns = document.querySelectorAll('.filter-btn');
  const postCards = document.querySelectorAll('.blog-post-card');

  filterBtns.forEach(btn => {
    btn.addEventListener('click', function() {
      // Remove active class from all buttons
      filterBtns.forEach(b => b.classList.remove('active'));
      // Add active class to clicked button
      this.classList.add('active');

      const category = this.getAttribute('data-category');

      // Filter blog post cards
      postCards.forEach(card => {
        const cardCategories = card.getAttribute('data-categories');
        
        if (category === 'all' || cardCategories.includes(category)) {
          card.style.display = 'block';
          card.style.animation = 'fadeInUp 0.5s ease';
        } else {
          card.style.display = 'none';
        }
      });
    });
  });

  // Smooth scroll animation for filtered results
  const style = document.createElement('style');
  style.textContent = `
    @keyframes fadeInUp {
      from { 
        opacity: 0; 
        transform: translateY(20px); 
      }
      to { 
        opacity: 1; 
        transform: translateY(0); 
      }
    }
  `;
  document.head.appendChild(style);
});
</script>
