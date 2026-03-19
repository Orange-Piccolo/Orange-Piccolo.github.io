---
title: "About Me"
layout: splash
permalink: /about-me/
---
Badda Bing Badda Boom
{% include figure image_path="/assets/images/Acid_Spray_Asset_PNG.png" alt="Placeholder alt EXPLOSION" caption="Placeholder caption EXPLOSION" %}

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
