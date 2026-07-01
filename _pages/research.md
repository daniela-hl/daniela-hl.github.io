---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

<style>
.research-details {
  border: 1px solid #d9d9d9;
  border-radius: 6px;
  padding: 0.5rem 0.85rem;
  margin: 0.1rem 0 0.5rem 0.6rem;
  background-color: transparent;
  font-size: 0.8rem;
}
.research-details summary {
  font-weight: 400;
  font-size: 0.8rem;
  cursor: pointer;
}
.research-details p {
  margin: 0.4rem 0;
}
.research-details ul {
  margin: 0.25rem 0 0.4rem 1.2rem;
  padding: 0;
}
.publication-list li {
  margin-bottom: 0.4rem;
}
</style>


## Research overview
My research is at the intersection of applied probability and optimization. Specifically, I study delay in a variety of Stochastic Processing Networks (or queueing systems). I love developing novel analysis methodologies that allow better understanding of the delay or queue lengths distribution in queueing systems. In particular, I enjoy using Moment Generating Functions and most of my work is on heavy-traffic analysis.


## Publications

### Under Review

{% assign under_review = site.data.papers | where: "section", "under_review" | sort: "date" | reverse %}
<ol>
{% for p in under_review %}
  <li>{{ p.title }}
    <details class="research-details">
      <summary>Coauthored with
        {% for c in p.coauthors %}{% if c.url %}<a href="{{ c.url }}" target="_blank" rel="noopener">{{ c.name }}</a>{% else %}{{ c.name }}{% endif %}{% unless forloop.last %}{% if forloop.rindex == 2 %} and {% else %}, {% endif %}{% endunless %}{% endfor %}.
        Click for more information.
      </summary>
      <p><strong>Abstract:</strong></p>
      {% for para in p.abstract %}<p>{{ para }}</p>{% endfor %}
      <p><strong>Current status:</strong></p>
      {% if p.versions %}
        <ul>
        {% for v in p.versions %}
          <li>{{ v.status }} <a href="{{ v.url }}" target="_blank" rel="noopener">here</a>.</li>
        {% endfor %}
        </ul>
      {% else %}
        {% assign p_url = p.url %}
        {% unless p_url contains '://' %}{% assign p_url = p_url | prepend: site.baseurl %}{% endunless %}
        <p>{{ p.status_text }} The latest version is available <a href="{{ p_url }}" target="_blank" rel="noopener">here</a>.</p>
      {% endif %}
    </details>
  </li>
{% endfor %}
</ol>

### Published work

{% if site.author.googlescholar %}
<div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}" target="_blank" rel="noopener noreferrer">my Google Scholar profile</a>.</div>
{% endif %}

{% assign published = site.data.papers | where: "section", "published" | sort: "date" | reverse %}
<ol class="publication-list" reversed>
{% for p in published %}
  <li>
    {% if p.url %}
      {% assign p_url = p.url %}
      {% unless p_url contains '://' %}{% assign p_url = p_url | prepend: site.baseurl %}{% endunless %}
      <a href="{{ p_url }}"{% if p.url contains '://' %} target="_blank" rel="noopener noreferrer"{% endif %}>{{ p.title }}</a>
    {% else %}
      {{ p.title }}
    {% endif %}
    {% if p.venue %} &mdash; <i>{{ p.venue }}</i>{% endif %}
    {% if p.year %}, {{ p.year }}{% endif %}
    {% if p.note %} <strong>({{ p.note }})</strong>{% endif %}
    {% if p.abstract %}
    <details class="research-details">
      {% if p.coauthors %}
      <summary>Coauthored with
        {% for c in p.coauthors %}{% if c.url %}<a href="{{ c.url }}" target="_blank" rel="noopener">{{ c.name }}</a>{% else %}{{ c.name }}{% endif %}{% unless forloop.last %}{% if forloop.rindex == 2 %} and {% else %}, {% endif %}{% endunless %}{% endfor %}.
        Click for more information.
      </summary>
      {% else %}
      <summary>Click for more information.</summary>
      {% endif %}
      <p><strong>Abstract:</strong></p>
      {% for para in p.abstract %}<p>{{ para }}</p>{% endfor %}
    </details>
    {% endif %}
  </li>
{% endfor %}
</ol>
