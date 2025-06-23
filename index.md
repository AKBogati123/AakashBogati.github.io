---
layout: default
title: "Home"
---

<div class="homepage">
  <!-- Hero Section -->
  <section class="hero-section">
    <div class="hero-content">
      <div class="hero-text">
        <div class="hero-badge">
          <span class="status-dot"></span>
          Available for opportunities
        </div>
        <h1 class="hero-title">Building the Future, One Line at a Time</h1>
        <p class="hero-subtitle">Full-Stack Developer & Technical Writer</p>
        <p class="hero-description">
          Welcome to my digital space where I share practical development insights, real-world solutions, 
          and lessons learned from building scalable applications. Join thousands of developers who read my content to level up their skills.
        </p>
        <div class="hero-stats">
          <div class="stat">
            <span class="stat-number">{{ site.posts.size }}+</span>
            <span class="stat-label">Articles</span>
          </div>
          <div class="stat">
            <span class="stat-number">5k+</span>
            <span class="stat-label">Readers</span>
          </div>
          <div class="stat">
            <span class="stat-number">3+</span>
            <span class="stat-label">Years Writing</span>
          </div>
        </div>
        <div class="hero-buttons">
          <a href="{{ '/blog/' | relative_url }}" class="btn-primary">
            <span>📚 Explore Articles</span>
          </a>
          <a href="{{ '/about/' | relative_url }}" class="btn-secondary">
            <span>👨‍💻 About Me</span>
          </a>
        </div>
      </div>
      <div class="hero-visual">
        <div class="code-window">
          <div class="window-header">
            <div class="window-controls">
              <div class="control close"></div>
              <div class="control minimize"></div>
              <div class="control maximize"></div>
            </div>
            <div class="window-title">main.py</div>
          </div>
          <div class="code-content">
            <div class="code-line"><span class="keyword">def</span> <span class="function">create_impact</span>():</div>
            <div class="code-line">    <span class="keyword">return</span> {</div>
            <div class="code-line">        <span class="string">"code"</span>: <span class="string">"clean & scalable"</span>,</div>
            <div class="code-line">        <span class="string">"writing"</span>: <span class="string">"practical & clear"</span>,</div>
            <div class="code-line">        <span class="string">"impact"</span>: <span class="string">"developers helped"</span></div>
            <div class="code-line">    }</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Value Proposition Section -->
  <section class="value-section">
    <div class="container">
      <h2 class="section-title">What Makes This Blog Different</h2>
      <div class="value-grid">
        <div class="value-card">
          <div class="value-icon">🎯</div>
          <h3>Real-World Focus</h3>
          <p>No theoretical fluff. Every tutorial and guide comes from actual projects and real challenges I've solved in production environments.</p>
        </div>
        
        <div class="value-card">
          <div class="value-icon">⚡</div>
          <h3>Actionable Content</h3>
          <p>Step-by-step guides you can implement immediately. Each post includes working code examples and practical tips you can use today.</p>
        </div>
        
        <div class="value-card">
          <div class="value-icon">🚀</div>
          <h3>Modern Tech Stack</h3>
          <p>Stay ahead with the latest technologies. I cover cutting-edge tools, frameworks, and best practices that matter in today's development landscape.</p>
        </div>
        
        <div class="value-card">
          <div class="value-icon">🤝</div>
          <h3>Developer Community</h3>
          <p>Join a growing community of developers. Share insights, ask questions, and learn together in a supportive environment.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Featured Posts Section -->
  <section class="featured-posts">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Latest Articles</h2>
        <p class="section-subtitle">Fresh insights from the development trenches</p>
      </div>
      
      <div class="posts-grid">
        {% for post in site.posts limit:6 %}
        <article class="post-card">
          <div class="post-meta">
            <time class="post-date">{{ post.date | date: "%b %d" }}</time>
            {% if post.categories.size > 0 %}
            <span class="post-category">{{ post.categories[0] }}</span>
            {% endif %}
          </div>
          
          <h3 class="post-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </h3>
          
          {% if post.excerpt %}
          <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 15 }}</p>
          {% endif %}
          
          <div class="post-footer">
            <div class="post-stats">
              {% assign read_time = post.content | number_of_words | divided_by: 200 %}
              {% if read_time == 0 %}{% assign read_time = 1 %}{% endif %}
              <span>📖 {{ read_time }} min read</span>
              <span>📝 {{ post.content | number_of_words }} words</span>
            </div>
            <a href="{{ post.url | relative_url }}" class="read-more-btn">
              Read Article →
            </a>
          </div>
        </article>
        {% endfor %}
      </div>
      
      <div class="section-footer">
        <a href="{{ '/blog/' | relative_url }}" class="btn-primary">View All Articles</a>
      </div>
    </div>
  </section>

  <!-- Topics Section -->
  <section class="topics-section">
    <div class="container">
      <h2 class="section-title">Explore by Topic</h2>
      <div class="topics-grid">
        {% assign sorted_categories = site.categories | sort: 1 %}
        {% for category in sorted_categories %}
        <a href="{{ '/blog/' | relative_url }}#{{ category[0] | slugify }}" class="topic-card">
          <div class="topic-icon">
            {% case category[0] %}
              {% when 'programming' %}🖥️
              {% when 'python' %}🐍
              {% when 'javascript' %}⚡
              {% when 'web-development' %}🌐
              {% when 'data-structures' %}📊
              {% when 'algorithms' %}🧮
              {% when 'oop' %}🏗️
              {% else %}📝
            {% endcase %}
          </div>
          <h3 class="topic-name">{{ category[0] | capitalize }}</h3>
          <p class="topic-count">{{ category[1].size }} article{% if category[1].size != 1 %}s{% endif %}</p>
        </a>
        {% endfor %}
      </div>
    </div>
  </section>

  <!-- Newsletter Section -->
  <section class="newsletter-section">
    <div class="container">
      <div class="newsletter-content">
        <div class="newsletter-text">
          <h2>Stay Updated</h2>
          <p>Get notified when I publish new articles about web development, programming tutorials, and tech insights. No spam, unsubscribe anytime.</p>
        </div>
        <div class="newsletter-form">
          <form action="#" method="post" class="subscription-form">
            <input type="email" placeholder="Enter your email address" class="email-input" required>
            <button type="submit" class="subscribe-btn">Subscribe</button>
          </form>
          <p class="newsletter-note">Join 1000+ developers getting weekly insights</p>
        </div>
      </div>
    </div>
  </section>
</div>

<style>
/* Reset and base styles */
.homepage {
  width: 100%;
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

/* Hero Section */
.hero-section {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 6rem 0 4rem;
  position: relative;
  overflow: hidden;
}

.hero-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 20% 20%, rgba(255,255,255,0.1) 2px, transparent 2px),
    radial-gradient(circle at 80% 80%, rgba(255,255,255,0.1) 3px, transparent 3px);
  background-size: 100px 100px, 150px 150px;
  animation: float 20s infinite linear;
}

@keyframes float {
  0% { transform: translateX(-50px); }
  100% { transform: translateX(50px); }
}

.hero-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 4rem;
  align-items: center;
  position: relative;
  z-index: 2;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(255, 255, 255, 0.15);
  padding: 0.5rem 1rem;
  border-radius: 2rem;
  font-size: 0.9rem;
  font-weight: 500;
  margin-bottom: 2rem;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #22c55e;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.7; transform: scale(1.1); }
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  margin-bottom: 1rem;
  line-height: 1.1;
  background: linear-gradient(135deg, #ffffff, #f0f9ff);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.hero-subtitle {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  opacity: 0.9;
  font-weight: 600;
}

.hero-description {
  font-size: 1.1rem;
  margin-bottom: 2rem;
  opacity: 0.85;
  line-height: 1.7;
  max-width: 600px;
}

.hero-stats {
  display: flex;
  gap: 2rem;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}

.stat {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 2rem;
  font-weight: 700;
}

.stat-label {
  font-size: 0.9rem;
  opacity: 0.8;
  font-weight: 500;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn-primary, .btn-secondary {
  padding: 1rem 2rem;
  border-radius: 0.75rem;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1rem;
}

.btn-primary {
  background: white;
  color: #3b82f6;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.1);
  color: white;
  border: 2px solid rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.5);
}

/* Code Window */
.hero-visual {
  position: relative;
}

.code-window {
  background: #1e293b;
  border-radius: 1rem;
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
  transform: perspective(1000px) rotateY(-5deg) rotateX(5deg);
  transition: transform 0.3s ease;
}

.code-window:hover {
  transform: perspective(1000px) rotateY(0deg) rotateX(0deg);
}

.window-header {
  background: #334155;
  padding: 1rem;
  display: flex;
  align-items: center;
  gap: 1rem;
}

.window-controls {
  display: flex;
  gap: 0.5rem;
}

.control {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.control.close { background: #ef4444; }
.control.minimize { background: #f59e0b; }
.control.maximize { background: #10b981; }

.window-title {
  color: #94a3b8;
  font-size: 0.9rem;
  font-weight: 500;
}

.code-content {
  padding: 1.5rem;
  font-family: 'Monaco', 'Menlo', monospace;
  font-size: 0.9rem;
  line-height: 1.6;
}

.code-line {
  margin-bottom: 0.5rem;
  color: #e2e8f0;
}

.keyword { color: #f472b6; }
.function { color: #60a5fa; }
.string { color: #34d399; }

/* Value Section */
.value-section {
  padding: 6rem 0;
  background: #f8fafc;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  text-align: center;
  color: #1e293b;
  margin-bottom: 3rem;
}

.value-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.value-card {
  background: white;
  padding: 2.5rem;
  border-radius: 1.5rem;
  text-align: center;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
  border: 1px solid #e2e8f0;
  transition: all 0.3s ease;
}

.value-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
}

.value-icon {
  font-size: 3rem;
  margin-bottom: 1.5rem;
}

.value-card h3 {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: #1e293b;
}

.value-card p {
  color: #64748b;
  line-height: 1.6;
  font-size: 1rem;
}

/* Featured Posts */
.featured-posts {
  padding: 6rem 0;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-subtitle {
  color: #64748b;
  font-size: 1.1rem;
  margin-top: 1rem;
}

.posts-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.post-card {
  background: white;
  border-radius: 1.5rem;
  padding: 2rem;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
  border: 1px solid #e2e8f0;
  transition: all 0.3s ease;
}

.post-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
}

.post-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
}

.post-date {
  background: #f1f5f9;
  color: #64748b;
  padding: 0.5rem 1rem;
  border-radius: 2rem;
  font-size: 0.85rem;
  font-weight: 500;
}

.post-category {
  background: linear-gradient(135deg, #3b82f6, #1d4ed8);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 2rem;
  font-size: 0.8rem;
  font-weight: 500;
  text-transform: capitalize;
}

.post-title {
  margin-bottom: 1rem;
}

.post-title a {
  color: #1e293b;
  text-decoration: none;
  font-size: 1.4rem;
  font-weight: 600;
  line-height: 1.3;
  display: block;
}

.post-title a:hover {
  color: #3b82f6;
}

.post-excerpt {
  color: #64748b;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  font-size: 1rem;
}

.post-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 1rem;
  border-top: 1px solid #f1f5f9;
}

.post-stats {
  display: flex;
  gap: 1rem;
  color: #94a3b8;
  font-size: 0.85rem;
}

.read-more-btn {
  background: linear-gradient(135deg, #3b82f6, #1d4ed8);
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.2s ease;
}

.read-more-btn:hover {
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(59, 130, 246, 0.4);
}

.section-footer {
  text-align: center;
}

/* Topics Section */
.topics-section {
  padding: 6rem 0;
  background: #f8fafc;
}

.topics-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
}

.topic-card {
  background: white;
  padding: 2rem;
  border-radius: 1rem;
  text-align: center;
  text-decoration: none;
  color: inherit;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  border: 1px solid #e2e8f0;
  transition: all 0.3s ease;
}

.topic-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
}

.topic-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.topic-name {
  font-size: 1.1rem;
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 0.5rem;
}

.topic-count {
  color: #64748b;
  font-size: 0.9rem;
}

/* Newsletter Section */
.newsletter-section {
  padding: 4rem 0;
  background: linear-gradient(135deg, #1e293b, #334155);
  color: white;
}

.newsletter-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}

.newsletter-text h2 {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.newsletter-text p {
  font-size: 1.1rem;
  opacity: 0.9;
  line-height: 1.6;
}

.subscription-form {
  display: flex;
  gap: 1rem;
  margin-bottom: 1rem;
}

.email-input {
  flex: 1;
  padding: 1rem;
  border: 2px solid #475569;
  border-radius: 0.75rem;
  background: rgba(255, 255, 255, 0.1);
  color: white;
  font-size: 1rem;
  backdrop-filter: blur(10px);
}

.email-input::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.email-input:focus {
  outline: none;
  border-color: #3b82f6;
}

.subscribe-btn {
  background: linear-gradient(135deg, #3b82f6, #1d4ed8);
  color: white;
  padding: 1rem 2rem;
  border: none;
  border-radius: 0.75rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
}

.subscribe-btn:hover {
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(59, 130, 246, 0.4);
}

.newsletter-note {
  font-size: 0.9rem;
  opacity: 0.7;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .hero-content,
  .newsletter-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
}

@media (max-width: 768px) {
  .container {
    padding: 0 1rem;
  }
  
  .hero-section {
    padding: 4rem 0 3rem;
  }
  
  .hero-title {
    font-size: 2rem;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .btn-primary,
  .btn-secondary {
    width: 200px;
    justify-content: center;
  }
  
  .value-section,
  .featured-posts,
  .topics-section {
    padding: 4rem 0;
  }
  
  .posts-grid {
    grid-template-columns: 1fr;
  }
  
  .post-footer {
    flex-direction: column;
    gap: 1rem;
    align-items: flex-start;
  }
  
  .subscription-form {
    flex-direction: column;
  }
  
  .code-window {
    transform: none;
  }
}

@media (max-width: 480px) {
  .hero-stats {
    justify-content: center;
    gap: 1rem;
  }
  
  .post-card {
    padding: 1.5rem;
  }
  
  .value-card {
    padding: 2rem;
  }
  
  .hero-title {
    font-size: 1.8rem;
  }
}
</style>
