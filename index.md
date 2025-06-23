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
        <div class="hero-visual">
          <div class="code-animation">
            <div class="code-line">console.log("Hello World!");</div>
            <div class="code-line">function buildAmazingThings() {</div>
            <div class="code-line">  return "Let's code together!";</div>
            <div class="code-line">}</div>
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

    <!-- Recent Posts Section (for main content) -->
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
              <span class="read-time">{{ post.content | number_of_words | divided_by: 200 }} min read</span>
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
            <span>{{ post.content | number_of_words | divided_by: 200 }} min read</span>
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
          <a href="{{ '/blog/' | relative_url }}?category={{ category[0] | slugify }}" class="category-link">
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

    <!-- Newsletter Widget (Optional) -->
    <div class="sidebar-widget newsletter-widget">
      <h3 class="widget-title">📬 Stay Updated</h3>
      <p class="newsletter-description">Get the latest posts delivered to your inbox!</p>
      <form class="newsletter-form" action="#" method="post">
        <input type="email" placeholder="Your email" class="newsletter-input" required>
        <button type="submit" class="newsletter-btn">Subscribe</button>
      </form>
    </div>
  </aside>
</div>
