---
layout: page
title: "Blog"
menu: main
---

## Welcome to James Stone's Personal Blog

This site is still heavily under development... but it's *slowly* getting there. It has been years James, it is now 2017 and your last post was nearly 2 years ago. Get with it. 


{% assign loopindex = 0 %}
{% for page in site.posts %}  
   {% if page.type != 'hidden' %}
   {% assign loopindex = loopindex | plus: 1 %}
   {% assign rowfinder = loopindex | modulo: 3 %}
   {% if rowfinder == 1 %}
   <div class="row">
   {% endif %}
   <div class="one-third column post">
      <h3><a href="{{ page.url }}">{{ page.title }}</a></h3>
      <time datetime="{{ page.date | date_to_xmlschema }}">{{ page.date | date_to_long_string }}</time> <br>
      {{ page.excerpt | markdownify | replace:'height="','max-height="'}}
   </div>
   {% if rowfinder == 0 %}
   </div>
   {% endif %}
{% endif %}
{% endfor %}
{% if rowfinder != 0 %}
</div>
{% endif %}
    

