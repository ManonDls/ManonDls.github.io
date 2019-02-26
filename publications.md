---
layout: page
permalink: /publications/
title: 
---

Jump to [Publications](#peer-reviewed-publications), [Books](#books), [PhD Theses](#theses)

---
<br>

## Publications
{: style="color:grey; font-size: 120%; font-weight: bold; text-align: center;"}
{% assign year = 1980 %}

{% for pub in site.data.pubs.publications %}
{% if {{pub.year}} == {{year}} %} 
{% else %} 
---
{{pub.year}}
{: style="color:grey; font-size: 120%; font-weight: bold; text-align: left;"}
---
{% assign year = {{pub.year}} %}
{% endif %} 

<span style="color: #c90016">▶︎</span> {% if pub.pdf %}[**{{pub.title}}**]({{pub.pdf}}){% else %} **{{pub.title}}** {% endif %}
 <br>*{{pub.author}}*<br>
{% if {{pub.type}} == "article" %} <span style="text-decoration:underline">***{{pub.journal}}***</span>
{% elsif {{pub.type}} == "inproceeding" or {{pub.type}} == "incollection" %} in ***{{pub.booktitle}}***, eds. *{{pub.editor}}*
{% elsif {{pub.type}} == "phdthesis" %}**{{pub.school}}**, Ph. D Thesis
{% endif %} {% if pub.doi %} doi: *{{pub.doi}}* {% endif %}{% if pub.arxiv %} *{{pub.arxiv}}* {% endif %}({{pub.year}})
<br><br>
{% endfor %}

---
<br><br><br>
## Books
{: style="color:grey; font-size: 120%; font-weight: bold; text-align: center;"}
---
{% for pub in site.data.books.publications %}
{% if pub.pdf %}<span style="color: #c90016">▶︎</span> [**{{pub.title}}**]({{pub.pdf}}){% else %}**{{pub.title}}** {% endif %}
 <br>edited by {{pub.editor}}<br>
 {{pub.publisher}} {% if pub.doi %} doi: {{pub.doi}} {% endif %}({{pub.year}}) 
{% endfor %}


---
<br><br><br>
## Theses
{: style="color:grey; font-size: 120%; font-weight: bold; text-align: center;"}
---
{% for pub in site.data.theses.publications %}
{% if pub.pdf %}<span style="color: #c90016">▶︎</span> [**{{pub.title}}**]({{pub.pdf}}){% else %}**{{pub.title}}** {% endif %}<br>
 **{{pub.school}}**, Ph. D. thesis ({{pub.year}})
{% endfor %}


{% include new-window-fix.html %}
