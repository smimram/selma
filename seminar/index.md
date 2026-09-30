---
layout: default
title: Seminar
---

# Seminar

{% for s in site.data.seminar %}
<div class="seminar">
  {% if s.picture %}<img class="seminar-picture" src="{{ s.picture }}" alt="{{ s.speaker }}">{% endif %}
  <h3 class="seminar-title">{{ s.title }}</h3>
  <p class="seminar-speaker">
    {% if s.website %}<a href="{{ s.website }}">{{ s.speaker }}</a>{% else %}{{ s.speaker }}{% endif %}{% if s.lab %} ({{ s.lab }}){% endif %}
  </p>
  <p class="seminar-when">
    {{ s.date | date: "%A %-d %B %Y, %H:%M" }}{% if s.room %} — {{ s.room }}{% endif %}
  </p>
  {% if s.abstract %}<div class="seminar-abstract">{{ s.abstract | markdownify }}</div>{% endif %}
</div>
{% endfor %}
