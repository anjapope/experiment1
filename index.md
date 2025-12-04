---
layout: default
title: Home
---

<div class="showcase">
    <h2>Interactive Ivory Items Showcase</h2>
    <p>Welcome to our interactive showcase of ivory items. Explore the collection below.</p>
    
    <div class="items-grid">
        {% for item in site.items %}
        <div class="item-card">
            {% if item.image %}
            <div class="item-thumbnail">
                <img src="{{ item.image | relative_url }}" alt="{{ item.title }}">
            </div>
            {% endif %}
            <div class="item-info">
                <h3><a href="{{ item.url | relative_url }}">{{ item.title }}</a></h3>
                {% if item.excerpt %}
                <p>{{ item.excerpt }}</p>
                {% endif %}
            </div>
        </div>
        {% endfor %}
    </div>
</div>
