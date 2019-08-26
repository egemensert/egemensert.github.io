---
layout: post
title:  "<span style='margin-bottom:-15px; display:block; font-size:32px;'>Characterizing Political Participation, </span><span style='font-size:20px; display:block; margin-bottom:-20px;'> Turkish Parliamentary Elections as a Case Study </span>"
date:   2019-08-23 17:33:22 +0300
categories: politics turkey
---

<style>
.footer {
  background-color:#202A4F;
}

.footer a {
  color: white;
}

.footer small {
  color: white;
}

a {
  color:#202A4F;
}

</style>
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

Democracy is government by the people. Ideally, people choose their representatives
based on evaluating the candidates' agenda and determining which candidate is the best for them.
However, choosing the best candidate based on individual efforts is tiresome.
In practice, people gather in friends and family meetings and share
their political thoughts stemming from individual thinking,
people's social network and media. Consequently influencing and getting influenced
via the social network and media.

As people get influenced by the media, tailored propaganda can skew political
thought in public. If this media hold easily shareable, emotional messages, this skewing action might evolve
into a political epidemic, and in return skew public thought even more into the desired political
direction. This process may lead to a party gaining vast majority of votes in a region,
thereby having the same echoing thoughts getting reinforced (echo chambers)
and consequently having extremist polarization.

In this blog post, we present two metrics to measure a region's variety in political thought
and divergence of political behavior of one region from another region. Variety is measured
by the normalized entropy and divergence is measured by the Kullback-Leibler divergence
(metrics widely used in communications and computing). Let's start with the normalized entropy.

{% raw %}
  $$ \color{#242e2b}{H(P) = \frac{1}{log|P|} \sum_{p \in P} p ~ logp}$$
{% endraw %}
