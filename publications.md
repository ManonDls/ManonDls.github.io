---
layout: default
permalink: /publications/
title: 
---

<br /><br />

{% assign year = 1980 %}

{% for pub in site.data.pubs.publications %}
{% if {{pub.year}} == {{year}} %} 
{% else %} 
{{pub.year}}
{: style="color:black; font-size: 200%; text-align: center;"}
---
{% assign year = {{pub.year}} %}
{% endif %} 
**{{pub.pubnum}})** {% if pub.pdf %}[**{{pub.title}}**]({{pub.pdf | prepend: "/files/" site.url}})
{% else %}
**{{pub.title}}** 
{% endif %}
{{pub.author}}<br />
{% if {{pub.type}} == "article" %} *{{pub.journal}}*
{% elsif {{pub.type}} == "inproceeding" or {{pub.type}} == "incollection" %} in *{{pub.booktitle}}*, eds. *{{pub.editor}}*
{% elsif {{pub.type}} == "phdthesis" %} Ph. D Thesis, **{{pub.school}}**
{% endif %} ({{pub.year}})<br /><br />
{% endfor %}



