---
title: Cocktails by Spirit
description: Know which spirit you like but not what drink to have?  Use this listing to help you find out!
---
<link rel="stylesheet" href="css/overrides.css" />

{% for spirit in site.spirits %}

## {{ spirit.name | capitalize }}

{{ spirit.content }}

{% assign cocktails = site.cocktails | where: "spirits", spirit.name %}
{% for cocktail in cocktails %}
### [{{ cocktail.title }}]({{ cocktail.url }})

{{ cocktail.description }}
{% endfor %}

<div class="group-sep"></div>

{% endfor %}