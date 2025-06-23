layout: default
title: "Home"
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
<section class="recent-posts">
  <div class="container">
    <div class="section-header">
      <h2 class="section-title">📝 Latest Posts</h2>
      <a href="{{ '/blog/' | relative_url }}" class="view-all-link">View All Posts →</a>
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
      <a href="{{ post.url | relative_url }}" class="read-more">Read more →</a>
      <span class="read-time">{{ post.content | number_of_words | divided_by: 200 }} min read</span>
    </div>
  </article>
  {% endfor %}
  
  {% if site.posts.size == 0 %}
  <div class="no-posts-card">
    <div class="no-posts-icon">📝</div>
    <h3>Blog Coming Soon!</h3>
    <p>I'm working on some amazing content. Check back soon for insightful posts about development, programming, and tech!</p>
  </div>
  {% endif %}
</div>

{% if site.posts.size > 0 %}
<div class="view-all-center">
  <a href="{{ '/blog/' | relative_url }}" class="btn-primary">View All Posts</a>
</div>
{% endif %}
  </div>
</section>
<section class="technologies">
  <div class="container">
    <h2 class="section-title">🛠️ Technologies I Work With</h2>
<div class="tech-grid">
  <div class="tech-category">
    <h3>Frontend</h3>
    <div class="tech-tags">
      <span class="tech-tag">React</span>
      <span class="tech-tag">Vue.js</span>
      <span class="tech-tag">TypeScript</span>
      <span class="tech-tag">JavaScript</span>
    </div>
  </div>
  
  <div class="tech-category">
    <h3>Backend</h3>
    <div class="tech-tags">
      <span class="tech-tag">Python</span>
      <span class="tech-tag">Node.js</span>
      <span class="tech-tag">Django</span>
      <span class="tech-tag">FastAPI</span>
    </div>
  </div>
  
  <div class="tech-category">
    <h3>Tools & Cloud</h3>
    <div class="tech-tags">
      <span class="tech-tag">AWS</span>
      <span class="tech-tag">Docker</span>
      <span class="tech-tag">Git</span>
      <span class="tech-tag">Linux</span>
    </div>
  </div>
</div>
  </div>
</section>
<section class="cta-section">
  <div class="container">
    <div class="cta-content">
      <h2>🤝 Let's Connect & Build Together!</h2>
      <p>Got questions? Want to collaborate? Or just want to chat about tech?</p>
  <div class="connect-buttons">
    <a href="https://github.com/{{ site.github_username }}" class="social-btn">GitHub</a>
    <a href="mailto:{{ site.email }}" class="social-btn">Email</a>
    <a href="{{ '/about/' | relative_url }}" class="social-btn">About</a>
  </div>
</div>
  </div>
</section>
