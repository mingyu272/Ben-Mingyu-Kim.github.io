---
layout: armor
permalink: /
title: Home
home: true
---
<section class="armor-hero">
  <div class="armor-container armor-hero-grid">
    <div class="armor-hero-copy">
      <p class="armor-eyebrow"><span class="armor-rule"></span> AUTONOMY. INTELLIGENCE. IMPACT.</p>
      <h1>Robotic systems that<br>sense, learn, <em>coordinate,</em><br>and make decisions<br>under uncertainty.</h1>
      <p class="armor-hero-name">Autonomous Robotics &amp; Multi-Agent Operations Research (ARMOR) Lab</p>
      <p class="armor-hero-institution">Georgia Southern University<br>Department of Electrical and Computer Engineering</p>
      <div class="armor-actions"><a class="armor-button" href="{{ '/research/' | relative_url }}">Explore our research <span aria-hidden="true">→</span></a><a class="armor-text-link" href="{{ '/join-us/' | relative_url }}">Join the lab <span aria-hidden="true">→</span></a></div>
    </div>
    <figure class="armor-hero-visual">
      <div class="armor-visual-label"><span>CONNECTED AUTONOMY</span><span>FIELD ↔ INTELLIGENCE</span></div>
      <img src="{{ '/images/research_multirobot.png' | relative_url }}" alt="An aerial robot, surface vessel, underwater robot, and sensors coordinating across a maritime environment" width="1024" height="1024">
      <figcaption><span class="armor-status-dot"></span> Heterogeneous systems. Shared intelligence.</figcaption>
    </figure>
  </div>
</section>
<section class="armor-affiliation"><div class="armor-container"><span>GEORGIA SOUTHERN UNIVERSITY</span><span>Electrical &amp; Computer Engineering</span><span>Statesboro, Georgia</span></div></section>
<section class="armor-section armor-container">
  <div class="armor-section-heading"><div><p class="armor-eyebrow">OUR RESEARCH</p><h2>From individual robots<br>to collective intelligence.</h2></div><p>We connect robotics, sensing, and operations research to build autonomous systems that adapt to a changing world.</p></div>
  <div class="armor-thrust-grid">{% for thrust in site.data.research %}
    <a class="armor-thrust" href="{{ '/research/' | relative_url }}#{{ thrust.id }}"><span class="armor-number">{{ thrust.number }} / RESEARCH THRUST</span><h3>{{ thrust.title }}</h3><p>{{ thrust.description }}</p><span class="armor-card-link">Explore this thrust <span aria-hidden="true">→</span></span></a>
  {% endfor %}</div>
</section>
<section class="armor-band"><div class="armor-container armor-section">
  <div class="armor-section-heading"><div><p class="armor-eyebrow">RESEARCH IN PRACTICE</p><h2>Autonomy with a purpose.</h2></div><a class="armor-text-link" href="{{ '/projects/' | relative_url }}">View all projects →</a></div>
  <div class="armor-project-grid">{% for project in site.data.projects limit:3 %}<article class="armor-project"><p class="armor-eyebrow">{{ project.thrust }}</p><h3><a href="{{ '/projects/' | relative_url }}#{{ project.title | slugify }}">{{ project.title }}</a></h3><p>{{ project.description }}</p></article>{% endfor %}</div>
</div></section>
<section class="armor-section armor-container armor-director-summary">
  <div class="armor-logo-panel"><img src="{{ '/images/armor-logo3.png' | relative_url }}" alt="ARMOR Lab at Georgia Southern University" loading="lazy" width="1024" height="1024"></div>
  <div><p class="armor-eyebrow">PEOPLE BEHIND THE RESEARCH</p><h2>A shared ambition<br>for autonomous systems.</h2><p>ARMOR Lab brings together research in multi-robot systems, autonomous sensing, stochastic modeling, optimization, and control.</p><p>Directed by <strong>Mingyu (Ben) Kim, Ph.D.</strong><br>Assistant Professor, Georgia Southern University</p><a class="armor-text-link" href="{{ '/people/' | relative_url }}">Meet the lab →</a></div>
</section>
<section class="armor-container armor-section armor-news-section">
  <div class="armor-section-heading"><div><p class="armor-eyebrow">FROM THE LAB</p><h2>News &amp; milestones.</h2></div><a class="armor-text-link" href="{{ '/news/' | relative_url }}">All news →</a></div>
  {% assign recent_news = site.data.news | sort: 'date' | reverse %}
  <div class="armor-project-grid">{% for item in recent_news limit:3 %}{% include armor-news-card.html item=item %}{% endfor %}</div>
</section>
<section class="armor-container armor-recruit"><div><p class="armor-eyebrow">BUILD WHAT COMES NEXT</p><h2>Curious about autonomous systems?</h2><p>Explore research opportunities for Ph.D., master’s, and undergraduate students.</p></div><a class="armor-button" href="{{ '/join-us/' | relative_url }}">Join ARMOR Lab →</a></section>
