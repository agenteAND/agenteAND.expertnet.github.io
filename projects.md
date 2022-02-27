---
layout: page
title: Projects
subtitle: Simplifying Life One Application at a Time
---

<div>
{% assign projectsCategory = site.projects | group_by_exp:"project", "project.categories"  %}
{% for category in projectsCategory %}
<h4 class="post-teaser__month">
<strong>
{% if category.name %} 
- - - - -  {{ category.name }} - - - - - 
{% else %} 
{{ Print }} 
{% endif %}
</strong>
</h4>
<ul class="list-posts">
{% for project in category.items %}
<li class="post-teaser">
<a href="{{ project.url | prepend: site.baseurl }}">
<span class="post-teaser__title">{{ project.title }}</span>
<span class="post-teaser__date">{{ project.date | date: "%d %B %Y" }}</span>
</a>
</li>
{% endfor %}
</ul>
{% endfor %}
</div>