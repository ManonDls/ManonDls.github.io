---
layout: page
permalink: /publications/
title: 
---

Jump to [Publications](#peer-reviewed-publications), [Books](#books), [PhD Theses](#theses)

---

## Peer reviewed publications

{% assign year = 1980 %}

{% for pub in site.data.pubs.publications %}
{% if {{pub.year}} == {{year}} %} 
{% else %} 
{{pub.year}}
{: style="color:grey; font-size: 120%; font-weight: bold; text-align: center;"}

{% assign year = {{pub.year}} %}
{% endif %} 

<span style="color: #c90016">▶︎</span> {% if pub.pdf %}[**{{pub.title}}**]({{pub.pdf}}){% else %} **{{pub.title}}** {% endif %}
 -- {{pub.author}} --
{% if {{pub.type}} == "article" %} ***{{pub.journal}}***
{% elsif {{pub.type}} == "inproceeding" or {{pub.type}} == "incollection" %} in ***{{pub.booktitle}}***, eds. *{{pub.editor}}*
{% elsif {{pub.type}} == "phdthesis" %} Ph. D Thesis, **{{pub.school}}**
{% endif %} {% if pub.doi %} -- DOI: {{pub.doi}} {% endif %}{% if pub.arxiv %} -- *{{pub.arxiv}}* {% endif %}

{% endfor %}

---
## Books

{% for pub in site.data.books.publications %}
{% if pub.pdf %}<span style="color: #c90016">■</span> [**{{pub.title}}**]({{pub.pdf}}){% else %}**{{pub.title}}** {% endif %}
 -- edited by {{pub.editor}} -- {{pub.publisher}}
 -- ({{pub.year}}) {% if pub.doi %} -- DOI: {{pub.doi}} {% endif %}
{% endfor %}


---
## Theses

{% for pub in site.data.theses.publications %}
{% if pub.pdf %}<span style="color: #c90016">■</span> [**{{pub.title}}**]({{pub.pdf}}){% else %}**{{pub.title}}** {% endif %}
 -- PhD thesis, **{{pub.school}}** -- ({{pub.year}})
{% endfor %}

{% include new-window-fix.html %}
