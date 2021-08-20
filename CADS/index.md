---
layout: default
title: CADS
---

# Hellow {{ page.url }} or {{ page.title }} or {{ page.handle }}

{% assign redirects = pages.CADS.pages | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

  > {{ page.title | escape }}

  ---
{% endfor %}

## pages.CADS

{% assign redirects = pages.CADS | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

  > {{ page.title | escape }}

  ---
{% endfor %}

## site.pages.CADS

{% assign redirects = site.pages.CADS | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

  > {{ page.title | escape }}

  ---
{% endfor %}

## pages

{% assign redirects = pages | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

  > {{ page.title | escape }}

  ---
{% endfor %}
