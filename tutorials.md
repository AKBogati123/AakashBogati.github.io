---
layout: page
title: "Tutorials"
permalink: /tutorials/
---

<style>
.tutorials-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.tutorials-hero {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 4rem 2rem;
  margin: -2rem -2rem 4rem -2rem;
  border-radius: 0 0 2rem 2rem;
  text-align: center;
}

.tutorials-hero h1 {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.tutorials-hero p {
  font-size: 1.2rem;
  opacity: 0.9;
  max-width: 600px;
  margin: 0 auto;
}

.categories-filter {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.category-btn {
  background: white;
  color: #64748b;
  padding: 0.75rem 1.5rem;
  border-radius: 2rem;
  text-decoration: none;
  font-weight: 500;
  border: 2px solid #e2e8f0;
  transition: all 0.3s ease;
  cursor: pointer;
}

.category-btn:hover,
.category-btn.active {
  background: #3b82f6;
  color: white;
  border-color: #3b82f6;
  transform: translateY(-2px);
}

.tutorials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.tutorial-card {
  background: white;
  border-radius: 1rem;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0,0,0,0.08);
  border: 1px solid #e2e8f0;
  transition: all 0.3s ease;
  position: relative;
}

.tutorial-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0,0,0,0.15);
}

.tutorial-header {
  background: linear-gradient(135deg, #3b82f6, #1d4ed8);
  padding: 1.5rem;
  color: white;
  position: relative;
}

.tutorial-level {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: rgba(255, 255, 255, 0.2);
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 1rem;
  font-size: 0.75rem;
  font-weight: 500;
}

.tutorial-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.tutorial-title {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: white;
}

.tutorial-description {
  opacity: 0.9;
  font-size: 1rem;
  line-height: 1.5;
}

.tutorial-content {
  padding: 1.5rem;
}

.tutorial-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tutorial-category {
  background: #f1f5f9;
  color: #475569;
  padding: 0.25rem 0.75rem;
  border-radius: 1rem;
  font-size: 0.75rem;
  font-weight: 500;
}

.tutorial-duration {
  color: #64748b;
  font-size: 0.875rem;
  display: flex;
  align-items: center;
  gap: 0.25rem;
}

.tutorial-topics {
  margin-bottom: 1.5rem;
}

.tutorial-topics h4 {
  font-size: 1rem;
  color: #1e293b;
  margin-bottom: 0.5rem;
}

.topics-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.topic-tag {
  background: #e0f2fe;
  color: #0277bd;
  padding: 0.25rem 0.5rem;
  border-radius: 0.5rem;
  font-size: 0.75rem;
  font-weight: 500;
}

.tutorial-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 1rem;
  border-top: 1px solid #f1f5f9;
}

.start-tutorial-btn {
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

.start-tutorial-btn:hover {
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(59, 130, 246, 0.4);
}

.tutorial-progress {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #64748b;
  font-size: 0.875rem;
}

.coming-soon-card {
  background: linear-gradient(135deg, #f8fafc, #e2e8f0);
  border: 2px dashed #cbd5e1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 3rem 2rem;
  min-height: 300px;
}

.coming-soon-card .icon {
  font-size: 3rem;
  margin-bottom: 1rem;
  opacity: 0.6;
}

.coming-soon-card h3 {
  color: #475569;
  margin-bottom: 0.5rem;
}

.coming-soon-card p {
  color: #64748b;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .tutorials-container {
    padding: 0 1rem;
  }
  
  .tutorials-hero {
    margin: -1rem -1rem 3rem -1rem;
    padding: 3rem 1rem;
  }
  
  .tutorials-hero h1 {
    font-size: 2rem;
  }
  
  .tutorials-grid {
    grid-template-columns: 1fr;
  }
  
  .categories-filter {
    flex-direction: column;
    align-items: center;
  }
  
  .tutorial-meta, .tutorial-footer {
    flex-direction: column;
    align-items: flex-start;
    gap: 1rem;
  }
}
</style>

<div class="tutorials-container">
  <div class="tutorials-hero">
    <h1>📚 Developer Tutorials</h1>
    <p>Step-by-step guides to master web development, from beginner basics to advanced techniques</p>
  </div>

  <div class="categories-filter">
    <button class="category-btn active" data-category="all">All Tutorials</button>
    <button class="category-btn" data-category="frontend">Frontend</button>
    <button class="category-btn" data-category="backend">Backend</button>
    <button class="category-btn" data-category="fullstack">Full-Stack</button>
    <button class="category-btn" data-category="tools">Tools & DevOps</button>
  </div>

  <div class="tutorials-grid">
    <!-- React Tutorial -->
    <div class="tutorial-card" data-category="frontend">
      <div class="tutorial-header">
        <div class="tutorial-level">Beginner</div>
        <div class="tutorial-icon">⚛️</div>
        <h3 class="tutorial-title">React Fundamentals</h3>
        <p class="tutorial-description">Learn React from scratch with hands-on examples and real projects</p>
      </div>
      <div class="tutorial-content">
        <div class="tutorial-meta">
          <span class="tutorial-category">Frontend</span>
          <span class="tutorial-duration">⏱️ 4 hours</span>
        </div>
        <div class="tutorial-topics">
          <h4>What you'll learn:</h4>
          <div class="topics-list">
            <span class="topic-tag">Components</span>
            <span class="topic-tag">Props & State</span>
            <span class="topic-tag">Hooks</span>
            <span class="topic-tag">Event Handling</span>
          </div>
        </div>
        <div class="tutorial-footer">
          <a href="#" class="start-tutorial-btn">
            Start Tutorial <span>🚀</span>
          </a>
          <div class="tutorial-progress">
            <span>📊 0/12 lessons</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Python Tutorial -->
    <div class="tutorial-card" data-category="backend">
      <div class="tutorial-header">
        <div class="tutorial-level">Beginner</div>
        <div class="tutorial-icon">🐍</div>
        <h3 class="tutorial-title">Python for Web Development</h3>
        <p class="tutorial-description">Master Python fundamentals and build web applications with Django</p>
      </div>
      <div class="tutorial-content">
        <div class="tutorial-meta">
          <span class="tutorial-category">Backend</span>
          <span class="tutorial-duration">⏱️ 6 hours</span>
        </div>
        <div class="tutorial-topics">
          <h4>What you'll learn:</h4>
          <div class="topics-list">
            <span class="topic-tag">Python Basics</span>
            <span class="topic-tag">Django Framework</span>
            <span class="topic-tag">Database Integration</span>
            <span class="topic-tag">API Development</span>
          </div>
        </div>
        <div class="tutorial-footer">
          <a href="#" class="start-tutorial-btn">
            Start Tutorial <span>🚀</span>
          </a>
          <div class="tutorial-progress">
            <span>📊 0/15 lessons</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Full-Stack Tutorial -->
    <div class="tutorial-card" data-category="fullstack">
      <div class="tutorial-header">
        <div class="tutorial-level">Intermediate</div>
        <div class="tutorial-icon">🌐</div>
        <h3 class="tutorial-title">Full-Stack MERN App</h3>
        <p class="tutorial-description">Build a complete application using MongoDB, Express, React, and Node.js</p>
      </div>
      <div class="tutorial-content">
        <div class="tutorial-meta">
          <span class="tutorial-category">Full-Stack</span>
          <span class="tutorial-duration">⏱️ 8 hours</span>
        </div>
        <div class="tutorial-topics">
          <h4>What you'll learn:</h4>
          <div class="topics-list">
            <span class="topic-tag">MERN Stack</span>
            <span class="topic-tag">Authentication</span>
            <span class="topic-tag">Database Design</span>
            <span class="topic-tag">Deployment</span>
          </div>
        </div>
        <div class="tutorial-footer">
          <a href="#" class="start-tutorial-btn">
            Start Tutorial <span>🚀</span>
          </a>
          <div class="tutorial-progress">
            <span>📊 0/20 lessons</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Docker Tutorial -->
    <div class="tutorial-card" data-category="tools">
      <div class="tutorial-header">
        <div class="tutorial-level">Intermediate</div>
        <div class="tutorial-icon">🐳</div>
        <h3 class="tutorial-title">Docker & DevOps</h3>
        <p class="tutorial-description">Learn containerization and deployment strategies for modern applications</p>
      </div>
      <div class="tutorial-content">
        <div class="tutorial-meta">
          <span class="tutorial-category">DevOps</span>
          <span class="tutorial-duration">⏱️ 5 hours</span>
        </div>
        <div class="tutorial-topics">
          <h4>What you'll learn:</h4>
          <div class="topics-list">
            <span class="topic-tag">Docker Basics</span>
            <span class="topic-tag">Docker Compose</span>
            <span class="topic-tag">CI/CD Pipelines</span>
            <span class="topic-tag">Production Deployment</span>
          </div>
        </div>
        <div class="tutorial-footer">
          <a href="#" class="start-tutorial-btn">
            Start Tutorial <span>🚀</span>
          </a>
          <div class="tutorial-progress">
            <span>📊 0/10 lessons</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Coming Soon Cards -->
    <div class="tutorial-card coming-soon-card" data-category="frontend">
      <div class="icon">🔜</div>
      <h3>Vue.js Masterclass</h3>
      <p>Coming Soon</p>
    </div>

    <div class="tutorial-card coming-soon-card" data-category="backend">
      <div class="icon">🔜</div>
      <h3>Node.js API Development</h3>
      <p>Coming Soon</p>
    </div>
  </div>
</div>

<script>
// Category filtering functionality
document.addEventListener('DOMContentLoaded', function() {
  const categoryBtns = document.querySelectorAll('.category-btn');
  const tutorialCards = document.querySelectorAll('.tutorial-card');

  categoryBtns.forEach(btn => {
    btn.addEventListener('click', function() {
      // Remove active class from all buttons
      categoryBtns.forEach(b => b.classList.remove('active'));
      // Add active class to clicked button
      this.classList.add('active');

      const category = this.getAttribute('data-category');

      // Filter tutorial cards
      tutorialCards.forEach(card => {
        if (category === 'all' || card.getAttribute('data-category') === category) {
          card.style.display = 'block';
          card.style.animation = 'fadeIn 0.5s ease';
        } else {
          card.style.display = 'none';
        }
      });
    });
  });
});
</script>

<style>
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>
