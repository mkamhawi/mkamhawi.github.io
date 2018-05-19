---
layout: page
title: About
class: 'post'
navigation: True
current: about
---

The personal blog of Mohamed Elkamhawi, Published with
<a href="https://jekyllrb.com/" target="_blank">Jekyll</a>
using <a href="https://github.com/biomadeira/jasper" target="_blank">Jasper</a>.

<div class="social-links">
{% if site.twitter %}
  <span>
    <a href="https://twitter.com/{{ site.twitter }}" target="_blank" class="social-link">
      <i class="fa fa-twitter" aria-hidden="true"></i>
    </a>
  </span>
{% endif %}

{% if site.github %}
  <span>
    <a href="https://github.com/{{ site.github }}" target="_blank" class="social-link">
      <i class="fa fa-github" aria-hidden="true"></i>
    </a>
  </span>
{% endif %}

{% if site.linkedin %}
  <span>
    <a href="https://www.linkedin.com/in/{{ site.linkedin }}" target="_blank" class="social-link">
      <i class="fa fa-linkedin" aria-hidden="true"></i>
    </a>
  </span>
{% endif %}
</div>