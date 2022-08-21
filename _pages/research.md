---
title: "QUREOS Lab - research"
layout: textlay
excerpt: "research"
sitemap: false
permalink: /research
---
<!--research.yml 에 내용을 입력하면 여기서는 출력만 담당하게 하고 싶음-->
# Research



{% assign number_printed = 0 %}

<!-- for문 시작-->
{% for research in site.data.research %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if research.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-12 clearfix">
 <div class="well">
  <pubtit>{{ research.title }}</pubtit>
  <p>{{ research.description }}</p>
  <p><strong><a href="{{ research.link.url }}">{{ research.link.display }}</a></strong></p>
  <p class="text-danger"><strong> {{ research.news1 }}</strong></p>
  <p> {{ research.news2 }}</p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}
<




