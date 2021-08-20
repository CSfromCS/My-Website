---
layout: default
title: CADS
---

# Hellow {{ page.slug}} or {{ page.title }}

{% assign redirects = site.CADS.pages | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

  > {{ page.title | escape }}

  ---
{% endfor %}
