---
layout: armor
title: Research
permalink: /research/
intro: Connecting distributed intelligence, uncertainty-aware sensing, and autonomous systems in the field.
---
<div class="armor-container armor-page-content">
<p class="armor-intro-copy">Our research develops real-time, probabilistic, and optimization-based algorithms for autonomous systems operating in uncertain and dynamic environments. Three complementary thrusts connect fundamental methods with applications in maritime awareness, environmental monitoring, and resilient infrastructure.</p>
{% for thrust in site.data.research %}
<section class="armor-research-row" id="{{ thrust.id }}">
  <div class="armor-research-image"><img src="{{ thrust.image | prepend: '/images/' | relative_url }}" alt="{{ thrust.alt }}" loading="lazy" width="1024" height="1024"></div>
  <div><p class="armor-eyebrow">RESEARCH THRUST {{ thrust.number }}</p><h2>{{ thrust.title }}</h2><p>{{ thrust.description }}</p>
  {% case thrust.id %}
  {% when 'multi-robot-intelligence' %}
  <p>We study how drones, surface vessels, underwater vehicles, and fixed sensors can collaborate in dynamic, data-limited settings.</p><ul><li>Cooperative mission planning and distributed control</li><li>Task allocation and communication for mixed robot teams</li><li>Decentralized estimation and optimization with time-varying constraints</li><li>Real-time adaptation for persistent monitoring and environmental exploration</li></ul>
  {% when 'uncertainty-aware-sensing' %}
  <p>We use Poisson processes and log-Gaussian Cox processes (LGCP) to characterize uncertain target arrivals and environmental processes, combining stochastic models with optimization for fixed and mobile sensor networks.</p><ul><li>Bayesian inference, state estimation, and heterogeneous data fusion</li><li>Anomaly detection for vessel traffic and coastal environments</li><li>Void-probability and variance-aware sensor-placement methods</li><li>Adaptive information acquisition and near-real-time sensor repositioning</li></ul>
  {% when 'autonomous-field-systems' %}
  <p>We connect planning and inference with autonomous aerial, surface, and sensor-network systems to support persistent observation in complex environments.</p><ul><li>USV–UAV collaborative sensing and adaptive water-quality sampling</li><li>Maritime domain awareness and distributed environmental monitoring</li><li>UAS mission planning for infrastructure inspection and emergency response</li><li>Digital-twin and data-driven modeling for prediction and decision support</li></ul>
  {% endcase %}</div>
</section>{% endfor %}
<div class="armor-callout"><h2>Explore the work.</h2><p>Learn about our project themes and find published results on Google Scholar.</p><div class="armor-actions"><a class="armor-button" href="{{ '/projects/' | relative_url }}">Projects →</a><a class="armor-text-link" href="{{ site.author.googlescholar | escape }}">Publications →</a></div></div>
</div>
