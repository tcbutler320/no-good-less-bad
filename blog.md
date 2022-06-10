---
layout: page
title: Blog
permalink: /blog/
---

I blog occasionally about information security. Most of my posts detail my vulnerability research and writeups of bug bounty or responsible disclosures. I sometimes compete in Capture the Flag competitions and will post writeups of past events.


<ul id="archive">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
    {% if year != y %}
    {% assign year = y %}
    <h2 class="blogyear">{{ y }}</h2>
   {% endif %}
  <li class="archiveposturl"><span><a href="{{ post.url }}">{{ post.title }}</a></span><br>
  <span class="postlower">

  <strong>Category:</strong>  
 
  <a href="/categories/{{ post.tag }}" title="{{ post.tag }}">{{ post.tag }}</a>&nbsp;

  <strong style="font-size:100%; font-family: 'Titillium Web', sans-serif; float:right; padding-right: .5em">{{ post.date  | date: "%b, %Y" }}</strong> 
  </span> 

  </li>
  {% endfor %}
</ul>
