---
layout: page
title: ""
---

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 4rem 2rem; margin-bottom: 3rem; border-radius: 12px; text-align: center;">
  <h1 style="font-size: 3rem; margin-bottom: 1rem; font-weight: 700;">👋 Hey, I'm Aakash Bogati</h1>
  <p style="font-size: 1.25rem; margin-bottom: 1rem; opacity: 0.9;">Full-Stack Developer & Technical Writer</p>
  <p style="font-size: 1.1rem; margin-bottom: 2rem; opacity: 0.85;">Turning complex code into simple stories. Join me as I share real development experiences, practical tutorials, and insights from the trenches of software engineering.</p>
  <div style="display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap;">
    <a href="/AakashBogati.github.io/blog/" style="background-color: white; color: #2563eb; padding: 0.75rem 1.5rem; border-radius: 0.5rem; text-decoration: none; font-weight: 600;">Read My Blog</a>
    <a href="/AakashBogati.github.io/about/" style="background-color: transparent; color: white; border: 2px solid rgba(255, 255, 255, 0.3); padding: 0.75rem 1.5rem; border-radius: 0.5rem; text-decoration: none; font-weight: 600;">About Me</a>
  </div>
</div>

## 🚀 What You'll Find Here

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem; margin: 2rem 0;">
  <div style="background-color: #f8fafc; padding: 1.5rem; border-radius: 1rem; text-align: center; border: 1px solid #e2e8f0;">
    <div style="font-size: 3rem; margin-bottom: 1rem;">💡</div>
    <h3 style="font-size: 1.25rem; font-weight: 600; margin-bottom: 1rem;">Practical Tutorials</h3>
    <p style="color: #64748b;">Step-by-step guides that actually work, tested in real projects</p>
  </div>
  
  <div style="background-color: #f8fafc; padding: 1.5rem; border-radius: 1rem; text-align: center; border: 1px solid #e2e8f0;">
    <div style="font-size: 3rem; margin-bottom: 1rem;">🔧</div>
    <h3 style="font-size: 1.25rem; font-weight: 600; margin-bottom: 1rem;">Problem-Solving</h3>
    <p style="color: #64748b;">Real challenges I've faced and the solutions that saved the day</p>
  </div>
  
  <div style="background-color: #f8fafc; padding: 1.5rem; border-radius: 1rem; text-align: center; border: 1px solid #e2e8f0;">
    <div style="font-size: 3rem; margin-bottom: 1rem;">🚀</div>
    <h3 style="font-size: 1.25rem; font-weight: 600; margin-bottom: 1rem;">Tech Insights</h3>
    <p style="color: #64748b;">Deep dives into technologies, frameworks, and best practices</p>
  </div>
  
  <div style="background-color: #f8fafc; padding: 1.5rem; border-radius: 1rem; text-align: center; border: 1px solid #e2e8f0;">
    <div style="font-size: 3rem; margin-bottom: 1rem;">📚</div>
    <h3 style="font-size: 1.25rem; font-weight: 600; margin-bottom: 1rem;">Learning Journey</h3>
    <p style="color: #64748b;">My experiences learning new tech - mistakes included!</p>
  </div>
</div>

## 📝 Latest Posts

<div style="margin: 2rem 0;">
  {% for post in site.posts limit:6 %}
  <div style="background-color: white; border-radius: 1rem; padding: 1.5rem; margin-bottom: 1.5rem; box-shadow: 0 1px 3px rgba(0,0,0,0.1); border: 1px solid #e2e8f0;">
    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem; flex-wrap: wrap;">
      <time style="color: #94a3b8; font-size: 0.875rem; font-weight: 500;">{{ post.date | date: "%b %d, %Y" }}</time>
      {% if post.categories.size > 0 %}
      <div style="display: flex; gap: 0.5rem; flex-wrap: wrap;">
        {% for category in post.categories limit:2 %}
        <span style="background-color: #f1f5f9; color: #64748b; padding: 0.25rem 0.5rem; border-radius: 0.25rem; font-size: 0.75rem; font-weight: 500;">{{ category }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </div>
    
    <h3 style="margin-bottom: 1rem;">
      <a href="{{ post.url | relative_url }}" style="color: #1e293b; text-decoration: none; font-size: 1.25rem; font-weight: 600; line-height: 1.3;">{{ post.title }}</a>
    </h3>
    
    {% if post.excerpt %}
    <p style="color: #64748b; line-height: 1.6; margin-bottom: 1rem;">{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
    {% endif %}
    
    <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap;">
      <a href="{{ post.url | relative_url }}" style="color: #2563eb; text-decoration: none; font-weight: 500;">Read more →</a>
      <span style="color: #94a3b8; font-size: 0.875rem;">{{ post.content | number_of_words | divided_by: 200 }} min read</span>
    </div>
  </div>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}
<div style="text-align: center; padding: 3rem; color: #64748b;">
  <div style="font-size: 4rem; margin-bottom: 1rem;">📝</div>
  <h3 style="font-size: 1.5rem; color: #1e293b; margin-bottom: 1rem;">Blog Coming Soon!</h3>
  <p>I'm working on some amazing content. Check back soon for insightful posts about development, programming, and tech!</p>
</div>
{% endif %}

<div style="text-align: center; margin: 2rem 0;">
  <a href="/AakashBogati.github.io/blog/" style="display: inline-block; padding: 12px 24px; background-color: #2563eb; color: white; text-decoration: none; border-radius: 6px; font-weight: 500;">View All Posts</a>
</div>

## 🛠️ Technologies I Work With

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem; margin: 2rem 0;">
  <div style="background-color: #f8fafc; padding: 1.5rem; border-radius: 1rem; text-align: center; border: 1px solid #e2e8f0;">
    <h3 style="font-size: 1.25rem; font-weight: 600; margin-bottom: 1rem;">Frontend</h3>
    <div style="display: flex; flex-wrap: wrap; gap: 0.5rem; justify-content: center;">
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">React</span>
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">Vue.js</span>
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">TypeScript</span>
    </div>
  </div>
  
  <div style="background-color: #f8fafc; padding: 1.5rem; border-radius: 1rem; text-align: center; border: 1px solid #e2e8f0;">
    <h3 style="font-size: 1.25rem; font-weight: 600; margin-bottom: 1rem;">Backend</h3>
    <div style="display: flex; flex-wrap: wrap; gap: 0.5rem; justify-content: center;">
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">Python</span>
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">Node.js</span>
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">Django</span>
    </div>
  </div>
  
  <div style="background-color: #f8fafc; padding: 1.5rem; border-radius: 1rem; text-align: center; border: 1px solid #e2e8f0;">
    <h3 style="font-size: 1.25rem; font-weight: 600; margin-bottom: 1rem;">Tools & Cloud</h3>
    <div style="display: flex; flex-wrap: wrap; gap: 0.5rem; justify-content: center;">
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">AWS</span>
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">Docker</span>
      <span style="background-color: #2563eb; color: white; padding: 0.5rem 1rem; border-radius: 0.5rem; font-size: 0.875rem; font-weight: 500;">Git</span>
    </div>
  </div>
</div>

## 🤝 Let's Connect!

<div style="text-align: center; padding: 2rem; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; border-radius: 12px; margin: 3rem 0;">
  <h2 style="font-size: 2rem; font-weight: 700; margin-bottom: 1rem; color: white;">Let's Connect & Build Together!</h2>
  <p style="font-size: 1.125rem; margin-bottom: 2rem; opacity: 0.9;">Got questions? Want to collaborate? Or just want to chat about tech?</p>
  
  <div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap;">
    <a href="https://github.com/AKBogati123" style="background-color: rgba(255, 255, 255, 0.1); color: white; padding: 0.75rem 1.5rem; border-radius: 0.5rem; text-decoration: none; font-weight: 500; border: 1px solid rgba(255, 255, 255, 0.2);">GitHub</a>
    <a href="mailto:your-email@example.com" style="background-color: rgba(255, 255, 255, 0.1); color: white; padding: 0.75rem 1.5rem; border-radius: 0.5rem; text-decoration: none; font-weight: 500; border: 1px solid rgba(255, 255, 255, 0.2);">Email</a>
    <a href="/AakashBogati.github.io/about/" style="background-color: rgba(255, 255, 255, 0.1); color: white; padding: 0.75rem 1.5rem; border-radius: 0.5rem; text-decoration: none; font-weight: 500; border: 1px solid rgba(255, 255, 255, 0.2);">About</a>
  </div>
</div>
