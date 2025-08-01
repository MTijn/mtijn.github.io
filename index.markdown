---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
---
{% for post in site.posts limit:1 %}
<article class="card mb-4 blog-post-card">
    <div class="card-body">
        <header>
          <h2 class="card-title">
            <a href="{{ post.url }}">{{ post.title }}</a>
          </h2>
          <div class="meta-info mb-3">
            <span class="meta me-3">
              <i class="fa fa-calendar"></i> {{ post.date | date_to_long_string }}
            </span>
            <span class="meta me-3">
              <i class="fa fa-user"></i> {{ post.author }}
            </span>
          </div>
        </header>
        <div class="card-text mb-3">
          <p>{{ post.content }}</p>
        </div>
        <div class="tags">
            {% for category in post.categories %}
            <span class="badge bg-secondary me-1">{{ category }}</span>
            {% endfor %}
        </div>
    </div>
</article>
{% endfor %}
