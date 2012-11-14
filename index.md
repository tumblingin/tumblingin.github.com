---
layout: page
title: Home
---

<!-- Show last 5 posts here -->
{% for post in site.posts limit: 5  %}
  <p class="date">{{ post.date | date_to_string }}</p>
  <h3><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h3>
  {{ post.content }}
  <p> Tags |
  {% for tag in post.tags %}
    <a href="#">{{ tag }}</a> |
  {% endfor %}
  </p>
  <hr/>
{% endfor %}

<ul>
{% for post in site.posts offset:5  %}
  <li>
    <div style="width: 100%">
  		<div style="float: left; width:100px">{{ post.date | date_to_string }}</div>
  		<div style="float: left; width:30px"> >> </div>
  		<div style="float: left;">
  			<a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
  		</div>
  		<br style="clear: left"></br>	
  	</div>	
  	</li>
{% endfor %}
</ul>