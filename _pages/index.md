---
title: "Torin Donnelly"
layout: splash
permalink: /
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/placeholder.png
  actions:
    - label: "Download CV"
      url: "https://drive.google.com/file/d/1ePqrAcar-abcMBgLCd7uo0HUbZDd929t/preview"
      target: "_blank"


excerpt: "Aspiring Game Design and Development student"
intro: 
  - excerpt: 'From here you can learn more about me:'
feature_row:
  - image_path: /assets/images/placeholder.png
    alt: "placeholder image 1"
    title: "Placeholder 1"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
  - image_path: /assets/images/placeholder.png
    alt: "placeholder image 2"
    title: "Placeholder 2"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/images/placeholder.png
    alt: "placeholder image 4"
    title: "Placeholder 3"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
{% assign skills = include.skills | default: page.skills %}
skills:
- name: "Unity"
  icon: "fab fa-fw fa-unity"
  badges: ["C#", "Game Development"]
  years: 1
- name: "Game Design"
- icon: "fas fa-fw fa-gamepad"
- badges: ["Game Mechanics", "Levels", "UI"]
- level_label: "Beginner"

{% if skills %}
<div class="skills {{ include.class }}">
  {% for skill in skills %}
    <div class="skill-card">
      {% if skill.icon %}
        <div class="skill-card__icon"><i class="{{ skill.icon }}" aria-hidden="true"></i></div>
      {% endif %}
      <div class="skill-card__body">
        <h3 class="skill-card__title">{{ skill.name }}</h3>
        {% if skill.badges %}
          <ul class="skill-card__badges">
            {% for badge in skill.badges %}
              <li>{{ badge }}</li>
            {% endfor %}
          </ul>
        {% endif %}
        {% if skill.text %}
          <p class="skill-card__text">{{ skill.text | markdownify | remove: "<p>" | remove: "</p>" }}</p>
        {% endif %}
        {% if skill.years %}
          <div class="skill-card__meta">
            <span class="skill-card__meta-label">Experience</span>
            <span class="skill-card__meta-value">{{ skill.years }} years</span>
          </div>
        {% elsif skill.level_label %}
          <div class="skill-card__meta">
            <span class="skill-card__meta-label">Level</span>
            <span class="skill-card__meta-value">{{ skill.level_label }}</span>
          </div>
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>
{% endif %}
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

