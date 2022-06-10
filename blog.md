---
layout: page
title: Blog
permalink: /blog/
---

<style>

ul.listing{list-style-type:none;margin-left:0px}
ul.listing li.listing-seperator{padding-top:15px;font-weight:bold;font-family:'Titillium Web', sans-serif;font-size:1.17em}
ul.listing li.listing-item time{color:#333;font-weight:500;text-transform:uppercase;padding-right:10px}
ul.listing li.listing-item a{color:#002F5F;font-weight:400;font-family:'Titillium Web', sans-serif}
ul#archive{list-style-type:none;margin:0 0 1em 0;padding:0}
ul#archive li{border-top:#999 1px dotted;border-bottom:#999 1px dotted;padding:.1em 0 .1em .5em}
ul#archive li:nth-child(even){background:#f9f9f9}
ul#archive li:nth-child(odd){background:#fff}
ul#archive h2{padding-top:0.5em}
ul#archive li.alt{background:#f6f6f6}
.archiveposturl{display:block;color:#333}
ul#archive li span a{color:#002F5F;font-weight:bold;font-family:'Titillium Web', sans-serif}
ul#archive li span.postlower{font-size:85%}
ul#archive li span.postlower a{color:#07c;font-weight:normal;font-family:"Open Sans", Helvetica, Arial, sans-serif}
article ul{list-style-type:none}
article ul>li:before{content:"–";position:absolute;margin-left:-1.1em}
article ul#archive>li:before{list-style-type:none;content:none}
/* ul {
    display: block;
    list-style-type: disc;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    padding-inline-start: 40px;
} */

</style>

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
