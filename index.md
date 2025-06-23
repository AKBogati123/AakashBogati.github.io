---
layout: default
title: "Home"
---

<div class="home-container">
  <!-- Main Content Area -->
  <div class="main-content">
    <!-- Hero Section -->
    <div class="hero-section">
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-title">👋 Hey, I'm Aakash Bogati</h1>
          <p class="hero-subtitle">Full-Stack Developer & Technical Writer</p>
          <p class="hero-description">
            Turning complex code into simple stories. Join me as I share real development experiences, 
            practical tutorials, and insights from the trenches of software engineering.
          </p>
          <div class="hero-buttons">
            <a href="{{ '/blog/' | relative_url }}" class="btn-primary">Read My Blog</a>
            <a href="{{ '/about/' | relative_url }}" class="btn-secondary">About Me</a>
          </div>
        </div>
      </div>
    </div>

    <!-- What You'll Find Section -->
    <section class="what-you-find">
      <div class="container">
        <h2 class="section-title">🚀 What You'll Find Here</h2>
        <div class="features-grid">
          <div class="feature-card">
            <div class="feature-icon">💡</div>
            <h3>Practical Tutorials</h3>
            <p>Step-by-step guides that actually work, tested in real projects</p>
          </div>
          
          <div class="feature-card">
            <div class="feature-icon">🔧</div>
            <h3>Problem-Solving</h3>
            <p>Real challenges I've faced and the solutions that saved the day</p>
          </div>
          
          <div class="feature-card">
            <div class="feature-icon">🚀</div>
            <h3>Tech Insights</h3>
            <p>Deep dives into technologies, frameworks, and best practices</p>
          </div>
          
          <div class="feature-card">
            <div class="feature-icon">📚</div>
            <h3>Learning Journey</h3>
            <p>My experiences learning new tech - mistakes included!</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Recent Posts Section -->
    <section class="recent-posts-main">
      <div class="container">
        <h2 class="section-title">📝 Featured Posts</h2>
        <div class="posts-grid">
          {% for post in site.posts limit:4 %}
          <article class="post-card">
            <div class="post-header">
              <time class="post-date">{{ post.date | date: "%b %d, %Y" }}</time>
              {% if post.categories.size > 0 %}
              <div class="post-categories">
                {% for category in post.categories limit:2 %}
                <span class="category-tag">{{ category }}</span>
                {% endfor %}
              </div>
              {% endif %}
            </div>
            
            <h3 class="post-title">
              <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h3>
            
            {% if post.excerpt %}
            <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
            {% endif %}
            
            <div class="post-footer">
              <a href="{{ post.url | relative_url }}" class="read-more">Read more →</a>
              {% assign read_time = post.content | number_of_words | divided_by: 200 %}
              {% if read_time == 0 %}{% assign read_time = 1 %}{% endif %}
              <span class="read-time">{{ read_time }} min read</span>
            </div>
          </article>
          {% endfor %}
        </div>
        
        <div class="view-all-center">
          <a href="{{ '/blog/' | relative_url }}" class="btn-primary">View All Posts</a>
        </div>
      </div>
    </section>
  </div>

  <!-- Sidebar -->
  <aside class="sidebar">
    <!-- Latest Blog Posts Widget -->
    <div class="sidebar-widget latest-posts-widget">
      <h3 class="widget-title">📖 Latest Articles</h3>
      <div class="latest-posts-list">
        {% for post in site.posts limit:5 %}
        <article class="sidebar-post">
          <div class="sidebar-post-meta">
            <time class="sidebar-post-date">{{ post.date | date: "%b %d" }}</time>
            {% if post.categories.size > 0 %}
            <span class="sidebar-post-category">{{ post.categories[0] }}</span>
            {% endif %}
          </div>
          <h4 class="sidebar-post-title">
            <a href="{{ post.url | relative_url }}">{{ post.title | truncatewords: 8 }}</a>
          </h4>
          <div class="sidebar-post-stats">
            {% assign read_time = post.content | number_of_words | divided_by: 200 %}
            {% if read_time == 0 %}{% assign read_time = 1 %}{% endif %}
            <span>{{ read_time }} min read</span>
          </div>
        </article>
        {% endfor %}
      </div>
      <div class="widget-footer">
        <a href="{{ '/blog/' | relative_url }}" class="view-all-link">View All Posts →</a>
      </div>
    </div>

    <!-- Categories Widget -->
    <div class="sidebar-widget categories-widget">
      <h3 class="widget-title">📂 Categories</h3>
      <ul class="categories-list">
        {% for category in site.categories %}
        <li class="category-item">
          <a href="{{ '/blog/' | relative_url }}" class="category-link">
            <span class="category-name">{{ category[0] }}</span>
            <span class="post-count">({{ category[1].size }})</span>
          </a>
        </li>
        {% endfor %}
      </ul>
    </div>

    <!-- Quick Links Widget -->
    <div class="sidebar-widget quick-links-widget">
      <h3 class="widget-title">🔗 Quick Links</h3>
      <ul class="quick-links-list">
        <li><a href="{{ '/tutorials/' | relative_url }}">📚 Tutorials</a></li>
        <li><a href="{{ '/about/' | relative_url }}">👨‍💻 About Me</a></li>
        <li><a href="https://github.com/{{ site.github_username }}" target="_blank">⚡ GitHub</a></li>
        <li><a href="mailto:{{ site.email }}">✉️ Contact</a></li>
      </ul>
    </div>
  </aside>
</div>

<style>
/* Homepage with sidebar layout */
.home-container {
  display: grid;
  grid-template-columns: 1fr 300px;
  gap: 3rem;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
}

.main-content {
  min-width: 0;
}

.sidebar {
  padding-top: 2rem;
  position: sticky;
  top: 100px;
  height: fit-content;
}

/* Sidebar Widgets */
.sidebar-widget {
  background: white;
  border-radius: 1rem;
  padding: 1.5rem;
  margin-bottom: 2rem;
  box-shadow: 0 2px 10px rgba(0,0,0,0.08);
  border: 1px solid #e2e8f0;
  transition: all 0.3s ease;
}

.sidebar-widget:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.12);
}

.widget-title {
  font-size: 1.2rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid #f1f5f9;
}

/* Latest Posts Widget */
.latest-posts-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.sidebar-post {
  padding-bottom: 1rem;
  border-bottom: 1px solid #f1f5f9;
}

.sidebar-post:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

.sidebar-post-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}

.sidebar-post-date {
  font-size: 0.8rem;
  color: #64748b;
  font-weight: 500;
}

.sidebar-post-category {
  background: #e0f2fe;
  color: #0277bd;
  padding: 0.15rem 0.5rem;
  border-radius: 0.75rem;
  font-size: 0.7rem;
  font-weight: 500;
}

.sidebar-post-title {
  margin-bottom: 0.5rem;
}

.sidebar-post-title a {
  color: #1e293b;
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 600;
  line-height: 1.3;
  display: block;
}

.sidebar-post-title a:hover {
  color: #3b82f6;
}

.sidebar-post-stats {
  font-size: 0.75rem;
  color: #94a3b8;
}

.widget-footer {
  margin-top: 1rem;
  padding-top: 1rem;
  border-top: 1px solid #f1f5f9;
  text-align: center;
}

.view-all-link {
  color: #3b82f6;
  text-decoration: none;
  font-weight: 500;
  font-size: 0.9rem;
}

.view-all-link:hover {
  color: #1d4ed8;
}

/* Categories Widget */
.categories-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.category-item {
  margin-bottom: 0.5rem;
}

.category-link {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 0.75rem;
  background: #f8fafc;
  border-radius: 0.5rem;
  text-decoration: none;
  color: #475569;
  transition: all 0.2s ease;
}

.category-link:hover {
  background: #e2e8f0;
  color: #1e293b;
}

.category-name {
  font-weight: 500;
}

.post-count {
  font-size: 0.8rem;
  color: #64748b;
}

/* Quick Links Widget */
.quick-links-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.quick-links-list li {
  margin-bottom: 0.5rem;
}

.quick-links-list a {
  display: block;
  padding: 0.5rem 0.75rem;
  background: #f8fafc;
  border-radius: 0.5rem;
  text-decoration: none;
  color: #475569;
  font-weight: 500;
  transition: all 0.2s ease;
}

.quick-links-list a:hover {
  background: #e2e8f0;
  color: #1e293b;
  transform: translateX(5px);
}

/* Mobile Responsiveness */
@media (max-width: 1024px) {
  .home-container {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .sidebar {
    position: static;
    order: -1;
  }
  
  .sidebar {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1rem;
  }
  
  .sidebar-widget {
    margin-bottom: 0;
  }
}

@media (max-width: 768px) {
  .home-container {
    padding: 0 1rem;
  }
  
  .sidebar {
    grid-template-columns: 1fr;
  }
}

/* Adjust existing sections for sidebar layout */
.hero-section,
.what-you-find,
.recent-posts-main {
  margin-bottom: 3rem;
}

.recent-posts-main .posts-grid {
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

.view-all-center {
  text-align: center;
  margin-top: 2rem;
}
</style>
