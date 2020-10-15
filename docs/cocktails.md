---
title: Cocktails by Category
description: A list of all the cocktails by the category that we've arbitrarily created and put them into.
---

<link rel="stylesheet" href="css/overrides.css" />

{% assign ordered_groups = site.groups | sort: "priority" %}
{% for grp in ordered_groups %}

## {{ grp.title }}

{{ grp.content }}

{% assign cocktails = site.cocktails | where: "groups", grp.name %}
{% for cocktail in cocktails %}
### [{{ cocktail.title }}]({{ cocktail.url }})

{{ cocktail.description }}
{% endfor %}

<div class="group-sep"></div>

{% endfor %}