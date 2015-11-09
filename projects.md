---
layout: page
title: projects
permalink: /projects/
weight: 3
---

{% assign sorted_projects = site.projects | sort:"weight" %}
{% for project in sorted_projects %}

<div class="project">
    <div class="thumbnail">
        {% if project.redirect %}
        <a href="{{ project_url }}" target="_blank">
        {% else %}
        <a href="{{ project.url | prepend:site.baseurl }}">
        {% endif %}
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend:site.baseurl }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}
        <span>
            <h1>{{ project.title }}</h1>
            <br/>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
</div>

{% endfor %}