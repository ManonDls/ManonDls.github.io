---
layout: page
permalink: /lala/
title: Publications
---

Jump to [Publications](#peer-reviewed-publications), [Thesis](#doctoral-thesis), [Media](#media-coverage), [Reviewing](#professional-service)

---

## Peer reviewed publications

{% assign thumbnail="right" %}

{% for pub in site.data.cv.publications %}
{% if pub.type == "article" %}
{{pub.author}}<br />
**{{pub.title}}**<br />
*{{pub.journal}}*
{% if pub.note %} *({{pub.note}})*
{% endif %} *{{pub.year}}*  [[web]({% if pub.internal %}{{pub.url | prepend: site.baseurl}}{% else %}{{pub.url}}{% endif %})] {% if pub.doi %}[[doi]({{pub.doi}})]{% endif %}
{% elsif pub.type == "inproceedings" or pub.type == "incollections"%}
{{pub.author}}<br />
**{{pub.title}}**<br />
in *{{pub.booktitle}}*, eds. *{{pub.editor}}*
*{{pub.year}}*  [[web]({% if pub.internal %}{{pub.url | prepend: site.baseurl}}{% else %}{{pub.url}}{% endif %})] {% if pub.doi %}[[doi]({{pub.doi}})]{% endif %}
{% endif %}
{% endfor %}

-----

## Doctoral thesis

**Algorithms & perceptual analysis for interactive free viewpoint image-based navigation** [[web]({{ "/research/thesis/" | prepend: site.baseurl}})]<br />
*Adviser: [George Drettakis](http://www-sop.inria.fr/members/George.Drettakis)* <br />
[INRIA](http://www.inria.fr/sophia), 2014

------

## Media coverage

{% for pub in site.data.cv.publications %}
{% if pub.media %}
- {{pub.title}} ({{pub.note}}, {{pub.year}}){% for article in pub.media %}
    - [{{article.url}}]({{article.url}}){% endfor %}
{% endif %}

{% endfor %}

------

## Professional service

- Conference reviews{% for review in site.data.cv.reviews.conference %}
    - {{review.title}} {% for y in review.years %} [{% if y.url %}[{{y.year}}]({{y.url}}){% else %}{{y.year}}{% endif %}] {% endfor %}<br />{% endfor %}

- Journal reviews{% for review in site.data.cv.reviews.journal %}
    - {{review.title}} {% for y in review.years %} [{% if review.url %}[{{y.year}}]({{review.url}}){% else %}{{y.year}}{% endif %}] {% endfor %}<br />{% endfor %}
