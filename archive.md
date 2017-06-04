---
layout: page
title: Archive 
permalink: /archive/
---
Demo site for [Jekyll Ideal Image Slider Include](https://github.com/jekylltools/jekyll-ideal-image-slider-include)

<h1 class="page-heading">Archive By Category</h1>
<ul class="tag_box inline">
  {% assign categories_list = site.categories %}
  {% if categories_list.first[0] == null %}
    {% for category in categories_list %}
        <li><a href="{{ BASE_PATH }}#{{ category }}-ref">
            {{ category | join: "/" }} <span>{{ site.categories[category].size }}</span>
        </a></li>
    {% endfor %}
  {% else %}
    {% for category in categories_list %}
        <li><a href="{{ BASE_PATH }}#{{ category[0] }}-ref">
            {{ category[0] | join: "/" }} <span>{{ category[1].size }}</span>
        </a></li>
    {% endfor %}
  {% endif %}
</ul>

<h1 class="page-heading">Archive By Tags</h1>
<ul class="tag_box inline">
  {% assign tags_list = site.tags %}
  {% if tags_list.first[0] == null %}
    {% for tag in tags_list %}
        <li><a href="{{ BASE_PATH }}#{{ tag }}-ref">{{ tag }} <span>{{ site.tags[tag].size }}</span></a></li>
    {% endfor %}
  {% else %}
    {% for tag in tags_list %}
        <li><a href="{{ BASE_PATH }}#{{ tag[0] }}-ref">{{ tag[0] }} <span>{{ tag[1].size }}</span></a></li>
    {% endfor %}
  {% endif %}

</ul>





{% for category in site.categories %}
  <h2 id="{{ category[0] }}-ref">{{ category[0] | join: "/" }}</h2>
  <ul>
  {% assign pages_list = category[1] %}
  {% for node in pages_list %}
    {% if node.title != null %}
      {% if group == null or group == node.group %}
        {% if page.url == node.url %}
        <li class="active"><a href="{{ BASE_PATH }}{{node.url}}" class="active">{{node.title}}</a></li>
        {% else %}
        <li><a href="{{ BASE_PATH }}{{node.url}}">{{node.title}}</a></li>
        {% endif %}
      {% endif %}
    {% endif %}
  {% endfor %}

  </ul>
{% endfor %}




{% for tag in site.tags %}
  <h2 id="{{ tag[0] }}-ref">{{ tag[0] }}</h2>
  <ul>
    {% assign pages_list = tag[1] %}
  {% for node in pages_list %}
    {% if node.title != null %}
      {% if group == null or group == node.group %}
        {% if page.url == node.url %}
        <li class="active"><a href="{{ BASE_PATH }}{{node.url}}" class="active">{{node.title}}</a></li>
        {% else %}
        <li><a href="{{ BASE_PATH }}{{node.url}}">{{node.title}}</a></li>
        {% endif %}
      {% endif %}
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}
~

