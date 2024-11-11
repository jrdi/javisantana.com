---
layout: base_data
---

<div class="container desierto">
  <div class="entry space">
  <h1>Inspiration — <span>@javisantana</span></h1>
  <p>I'm cofounder of <a href="https://tinybird.co">Tinybird</a>, a product to build realtime data products.
  These are the quotes that inspire me.</p>
  </div>


   {% for post in site.inspiration reversed %}
   {% if post.title != "Index" %}
        <div class="entry space" id="{{post.slug}}">
            {% if post.title %} 
            <h2>{{post.title}} <a href="#{{ post.slug }}">#</a></h2>
            {% endif %}
            <a href="{{ post.url }}"><span class="date">{{ post.date | date: "%b %d, %Y" }}</span></a>
            {{ post.content | split:'<!--break-->' | first }}
            {% if post.content contains '<!--break-->' %}
                <a href="{{ post.url }}">read more</a>
            {% endif %}
        </div>
    {%endif %}
  {% endfor %}

