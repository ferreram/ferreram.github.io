---
layout: page
permalink: /openings/
title: Openings
description: PhD and internship openings.
nav: true
nav_order: 3
---

<style>
  .opening { border-top: 1px solid var(--global-divider-color); padding: 1rem 0; }
  .opening h3 { margin: 0 0 0.25rem; font-size: 1.25rem; }
  .opening .meta { color: var(--global-text-color-light); font-size: 0.9rem; margin-bottom: 0.5rem; }
  .opening .kind { display: inline-block; padding: 0 0.5rem; margin-right: 0.5rem; border-radius: 3px; font-size: 0.8rem; font-weight: 600; color: var(--global-bg-color); background: var(--global-theme-color); }
  .opening.filled .kind { background: var(--global-text-color-light); }
</style>

I am regularly looking for internship and PhD students to join me in the Underwater Robotics Lab at [Ifremer](https://www.ifremer.fr/), in La Seyne-sur-Mer. Current openings are posted on this page.

{% assign openings = site.openings | sort: "date" | reverse %}
{% assign open_offers = openings | where: "status", "open" %}
{% assign past_offers = openings | where: "status", "filled" %}

## Current offers

{% if open_offers.size > 0 %}
{% for offer in open_offers %}

<div class="opening">
  <h3><span class="kind">{{ offer.type }}</span><a href="{{ offer.url | relative_url }}">{{ offer.title }}</a></h3>
  <div class="meta">
    {% if offer.start %}Start: {{ offer.start }}{% endif %}{% if offer.duration %} · {{ offer.duration }}{% endif %}{% if offer.location %} · {{ offer.location }}{% endif %}{% if offer.deadline %} · Apply by {{ offer.deadline | date: "%B %-d, %Y" }}{% endif %}
  </div>
  {% if offer.summary %}<p>{{ offer.summary }}</p>{% endif %}
</div>
{% endfor %}
{% else %}
I have no openings right now. If you are interested in an internship or a PhD in my research area, you are welcome to send me a spontaneous application.
{% endif %}

## How to apply

Email me at **maxime.ferrera@ifremer.fr** with your CV, a short cover letter explaining your interest, and your latest transcripts. Please mention the offer you are applying for in the subject line.

{% if past_offers.size > 0 %}

## Past offers

{% for offer in past_offers %}

<div class="opening filled">
  <h3><span class="kind">{{ offer.type }}</span><a href="{{ offer.url | relative_url }}">{{ offer.title }}</a></h3>
  <div class="meta">{% if offer.start %}{{ offer.start }}{% endif %}{% if offer.location %} · {{ offer.location }}{% endif %} · Filled</div>
</div>
{% endfor %}
{% endif %}
