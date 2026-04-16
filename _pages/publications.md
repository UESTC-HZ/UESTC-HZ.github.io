---
title: Publications
layout: default
permalink: /publications/
---

# Publications

{% assign pubs = site.bibliography | sort: "year" | reverse %}

{% for y in (2020..2030) reversed %}
  {% assign year_pubs = pubs | where: "year", y %}

  {% if year_pubs.size > 0 %}
## {{ y }}

    {% for p in year_pubs %}
- **{{ p.title }}**  
  {{ p.author }}  
  _{{ p.booktitle | default: p.journal }}_  
  {% if p.url %}[Link]({{ p.url }}){% endif %}
  {% if p.pdf %}[PDF]({{ p.pdf }}){% endif %}
  {% if p.code %}[Code]({{ p.code }}){% endif %}

    {% endfor %}
  {% endif %}
{% endfor %}
