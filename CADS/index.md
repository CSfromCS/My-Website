---
layout: default
---
{% assign thispageurl = page.url %}

# Hello {{ page.url | remove: "/" }}!

## site.pages with if contains

{% assign redirects = site.pages | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
{% if page.url contains thispageurl %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`
  > {{ page.title | escape }}
  ---
{% endif %}
{% endfor %}
