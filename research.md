---
layout: page
title: Research
permalink: /research/
---


{% include image.html url="/images/officejet.png" width=400 align="right" caption="Finding a cross-site scripting vulnerability in the HP OfficeJet 4630 Printer (CVE-2021-3441)" %}


In my free time, I search for vulnerabilities in open-source software, web applications, IoT, embedded devices, and for platforms with bug bounty programs. Most of my research to date includes vulnerabilities in web applications such as cross-site scripting, SQL injections, and authentication bypasses. I follow Google's Project Zero's [disclosure policy](https://googleprojectzero.blogspot.com/2021/04/policy-and-disclosure-2021-edition.html) when approaching vendors with vulnerabilities. In addition to my research here, I also publish proof of concept exploits on exploit-db and build out more comprehensive exploits on GitHub, such as exploitation frameworks like SendBirdy. 


<br>

<ul id="archive">
{% for entry in site.data.research %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
    {% if year != y %}
    {% assign year = y %}
    <h2 class="blogyear">{{ y }}</h2>
   {% endif %}

  <li class="archiveposturl"><span><a href="{{ entry.url }}">{{ entry.title }}</a></span><br>
  <span class="postlower">

  <strong>Category:</strong>  
 
  <a href="/categories/{{ entry.category }}" title="{{ entry.category }}">{{ entry.category}}</a>&nbsp;

  <strong style="font-size:100%; font-family: 'Titillium Web', sans-serif; float:right; padding-right: .5em">{{ entry.date  | date: "%b, %Y" }}</strong> 
  </span> 

  </li>
  {% endfor %}
</ul>
