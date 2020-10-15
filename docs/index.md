{% for grp in site.groups %}
## {{ grp.title }}

{{ grp.content }}

{% assign cocktails = site.cocktails | where: "groups", grp.name %}
{% for cocktail in cocktails %}
### [{{ cocktail.title }}]({{ cocktail.url }})

{{ cocktail.description }}
{% endfor %}

{% endfor %}
