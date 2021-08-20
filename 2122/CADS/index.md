---
---
{% assign thispageurl = page.url %}

# Hello {{ page.dir | remove: "/" }}!

{% assign redirects = site.pages | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
{% if page.url contains thispageurl %}
  [{{ page.url | remove_first: thispageurl }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`
  > {{ page.title | escape }}
  ---
{% endif %}
{% endfor %}
