---
layout: default
title: CADS
---
{% assign thispageurl = page.url %}

# Hellow {{ page.url | remove: "/" }} or {{ page.title }} or {{ page.handle }}

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

## site.pages

{% assign redirects = site.pages | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

  > {{ page.title | escape }}

  ---
{% endfor %}

## site.pages with if contains

{% assign redirects = site.pages | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
  {% if page.url contains thispageurl %}
    [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

    > {{ page.title | escape }}
  {% endif %}
  ---
{% endfor %}
