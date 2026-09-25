---
layout: default
---

<section class="hero" id="about">
  <!-- Add a square headshot named photo.jpg at the repo root; the image hides itself if the file is missing. -->
  <img src="{{ '/photo.jpg' | relative_url }}" alt="Taylla Theodoro" onerror="this.style.display='none'">
  <div markdown="1">
I am an R&D engineer on the [Computational Imaging](https://biohub.org/comp-imaging/people/) platform at the Chan Zuckerberg Biohub in San Francisco. I build tools that let microscopes follow living samples on their own, and data pipelines that turn large time-lapse datasets into something biologists can actually use.

Before the Biohub I did an M.Sc. in Computer Science at the University of Campinas (UNICAMP), advised by Alexandre Xavier Falcão, working on 4D MRI of the thorax to help radiologists spot pleural mesothelioma earlier. Part of that work was done with the PREDICT-Meso network at the University of Glasgow. My undergraduate degree is in Electrical Engineering from the State University of Londrina.
  </div>
</section>

<h2 id="research">Research highlights</h2>

{% for r in site.data.research %}
<div class="item">
  <div class="thumb">{% if r.thumb %}<img src="{{ r.thumb | relative_url }}" alt="">{% else %}{{ r.short }}{% endif %}</div>
  <div>
    <h3>{{ r.title }}</h3>
    <p class="meta">{{ r.authors }}. <i>{{ r.venue }}</i>, {{ r.year }}.</p>
    <p class="links">{% for l in r.links %}<a href="{{ l[1] }}">{{ l[0] }}</a>{% endfor %}</p>
    <p>{{ r.summary }}</p>
  </div>
</div>
{% endfor %}

<h2 id="publications">Publications</h2>
<ol class="pubs">
{% for p in site.data.publications %}
  <li>{{ p.authors }}. {{ p.title }}. <i>{{ p.venue }}</i>, {{ p.year }}.{% if p.url %} <a href="{{ p.url }}">link</a>{% endif %}</li>
{% endfor %}
</ol>
