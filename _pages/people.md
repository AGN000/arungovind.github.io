---
layout: page
permalink: /People/
title: People
roles: [Director, Ph.D., Master, Undergraduate]
nav: false
---

**Ph.D. Students**

Sourabh Yadav (2022 Spring --) 


**Master Students**

Harshitha Gorrepati (2022 Spring --) 

Tanuja Polineni (2021 Fall --)

<div class="people">

{% for y in page.roles %}
  <h2 class="roles">{{role}}</h2>
  {% bibliography -f papers -q @*[roles={{y}}]* %}
{% endfor %}

</div>

