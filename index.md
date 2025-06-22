---
layout: page
title: ""
---

<div class="hero-section">
  <div class="hero-content">
    <div class="hero-text">
      <h1 class="hero-title">👋 Hey, I'm Aakash Bogati</h1>
      <p class="hero-subtitle">Full-Stack Developer & Technical Writer</p>
      <p class="hero-description">Turning complex code into simple stories. Join me as I share real development experiences, practical tutorials, and insights from the trenches of software engineering.</p>
      <div class="hero-buttons">
        <a href="/blog/" class="btn-primary">Read My Blog</a>
        <a href="/about/" class="btn-secondary">About Me</a>
      </div>
    </div>
    <div class="hero-visual">
      <div class="code-snippet">
        <div class="code-header">
          <div class="code-dots">
            <span></span><span></span><span></span>
          </div>
          <span>main.py</span>
        </div>
        <div class="code-content">
          <span class="code-comment"># Building awesome things</span><br>
          <span class="code-keyword">def</span> <span class="code-function">create_impact</span>():<br>
          &nbsp;&nbsp;<span class="code-keyword">return</span> <span class="code-string">"One line at a time"</span>
        </div>
      </div>
    </div>
  </div>
</div>

<section class="what-you-find">
  <div class="container">
    <h2 class="section-title">What You'll Find Here</h2>
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

<section class="recent-posts">
  <div class="container">
    <div class="section-header">
      <h2 class="section-title">Latest Posts</h2>
      <a href="/blog/" class="view-all-link">View all posts →</a>
    </div>
    
    <div class="posts-grid">
      {% for post in site.posts limit:6 %}
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
        <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
        {% endif %}
        <div class="post-footer">
          <a href="{{ post.url | relative_url }}" class="read-more">Read more</a>
          <span class="read-time">{{ post.content | number_of_words | divided_by: 200 }} min read</span>
        </div>
      </article>
      {% endfor %}
    </div>
    
    {% if site.posts.size == 0 %}
    <div class="no-posts">
      <div class="no-posts-icon">📝</div>
      <h3>Blog Coming Soon!</h3>
      <p>I'm working on some amazing content. Check back soon for insightful posts about development, programming, and tech!</p>
    </div>
    {% endif %}
  </div>
</section>

<section class="tech-stack">
  <div class="container">
    <h2 class="section-title">Technologies I Work With</h2>
    <div class="tech-grid">
      <div class="tech-category">
        <h3>Frontend</h3>
        <div class="tech-items">
          <span class="tech-tag">React</span>
          <span class="tech-tag">Vue.js</span>
          <span class="tech-tag">TypeScript</span>
          <span class="tech-tag">Modern CSS</span>
        </div>
      </div>
      <div class="tech-category">
        <h3>Backend</h3>
        <div class="tech-items">
          <span class="tech-tag">Python</span>
          <span class="tech-tag">Node.js</span>
          <span class="tech-tag">Django</span>
          <span class="tech-tag">FastAPI</span>
        </div>
      </div>
      <div class="tech-category">
        <h3>Tools & Cloud</h3>
        <div class="tech-items">
          <span class="tech-tag">AWS</span>
          <span class="tech-tag">Docker</span>
          <span class="tech-tag">Git</span>
          <span class="tech-tag">PostgreSQL</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="cta-section">
  <div class="container">
    <div class="cta-content">
      <h2>Let's Connect & Build Together!</h2>
      <p>Got questions? Want to collaborate? Or just want to chat about tech?</p>
      <div class="connect-buttons">
        <a href="https://github.com/AKBogati123" class="social-btn github">
          <span>GitHub</span>
        </a>
        <a href="mailto:your-email@example.com" class="social-btn email">
          <span>Email</span>
        </a>
        <a href="#" class="social-btn linkedin">
          <span>LinkedIn</span>
        </a>
      </div>
    </div>
  </div>
</section>
