---
layout: page
title: 存档
permalink: /archive/
---
AA
{{ BASE_PATH| relative_url  }}
{{baseurl}}
BB

<h1 class="page-heading">By Category</h1>
<ul class="tag_box inline">
  {% assign categories_list = site.categories %}
  {% if categories_list.first[0] == null %}
    {% for category in categories_list %}
        <a href="{{ BASE_PATH }}#{{ category }}-ref">
            {{ category | join: "/" }} <span> ({{ site.categories[category].size }})</span>
        </a>
    {% endfor %}
  {% else %}
    {% for category in categories_list %}
        <a href="{{ BASE_PATH }}#{{ category[0] }}-ref">
            {{ category[0] | join: "/" }} <span> ({{ category[1].size }})</span>
        </a>
    {% endfor %}
  {% endif %}
</ul>

<h1 class="page-heading">By Tags</h1>
<ul class="tag_box inline">
  {% assign tags_list = site.tags %}
  {% if tags_list.first[0] == null %}
    {% for tag in tags_list %}
        <a href="{{ BASE_PATH }}#{{ tag }}-ref">{{ tag }} <span>({{ site.tags[tag].size }})</span></a>
    {% endfor %}
  {% else %}
    {% for tag in tags_list %}
        <a href="{{ BASE_PATH }}#{{ tag[0] }}-ref">{{ tag[0] }} <span>({{ tag[1].size }})</span></a>
    {% endfor %}
  {% endif %}

</ul>

<h1 class="page-heading">By Time</h1>
<ul class="tag_box inline">
  {% assign posts_collate = site.posts %}
  {% for post in posts_collate  %}
    {% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
    {% capture this_month %}{{ post.date | date: "%B" }}{% endcapture %}
    {% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}
    {% capture next_month %}{{ post.previous.date | date: "%B" }}{% endcapture %}
  
    {% if forloop.first %}
      <h2>{{this_year}}</h2>
      <h3>{{this_month}}</h3>
      <ul>
    {% endif %}
  
    <li><span>{{ post.date | date: "%B %e, %Y " }}</span>  <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  
    {% if forloop.last %}
      </ul>
    {% else %}
      {% if this_year != next_year %}
        </ul>
        <h2>{{next_year}}</h2>
        <h3>{{next_month}}</h3>
        <ul>
      {% else %}    
        {% if this_month != next_month %}
          </ul>
          <h3>{{next_month}}</h3>
          <ul>
        {% endif %}
      {% endif %}
    {% endif %}
  {% endfor %}
{% assign posts_collate = nil %}
 </ul>


{% for category in site.categories %}
  <h2 id="{{ category[0] }}-ref">{{ category[0] | join: "/" }}</h2>
  <ul>
  {% assign pages_list = category[1] %}
  {% for node in pages_list %}
    {% if node.title != null %}
      {% if group == null or group == node.group %}
        {% if page.url == node.url %}
        <li class="active"><a href="{{ site.baseurl }}{{node.url}}" class="active">{{node.title}}</a></li>
        {% else %}
        <li><a href="{{ site.baseurl }} {{node.url}}">{{node.title}}</a></li>
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
        <li class="active"><a href="/mobile{{node.url}}" class="active">{{node.title}}</a></li>
        {% else %}
        <li><a href="/mobile{{node.url}}">{{node.title}}</a></li>
        {% endif %}
      {% endif %}
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}







