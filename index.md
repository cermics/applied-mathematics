---
layout: page
cover-img: /assets/images/coriolis-reunion.jpg
---


Organizers: <a href="https://thebiglouloup.github.io/loucaspillaudvivien/">Loucas Pillaud-Vivien</a>,
<a href="https://urbain.vaes.uk">Urbain Vaes</a>.

See the <a href="https://calendar.google.com/calendar/embed?src=5e375da2e8afa22df729e4f6a1467993b104b67e8f44a4e6839d8dc1eba59524%40group.calendar.google.com&amp;ctz=Europe%2FParis">Google Agenda of the seminar</a>, and add the <a href="https://calendar.google.com/calendar/ical/5e375da2e8afa22df729e4f6a1467993b104b67e8f44a4e6839d8dc1eba59524%40group.calendar.google.com/public/basic.ics">iCal url</a> to your calendar.

### Upcoming seminars

|When| Who | Where|
|Tuesday, May 19 2026| Alice Marveggio| B211|

-------------------------

{% for link in site.data.applied-mathematics %}
{% if link.next == "yes" %}
{% if link.sem == "scommun" %}
{{ link.date | date : "%B %-d %Y" }}{% if link.hour != "void" %}, {{ link.hour }}, {% endif %}: {{ link.where }} **{{ link.author }}**,  
{% if link.univ %}{{ link.univ }}  {% endif %}
{% if link.title %}*{{ link.title }}*.{% endif %}
{% for sublink in link.PROG %}
 - {{ sublink.hour }}: **{{ sublink.author }}**,  
 {% if sublink.univ %}{{ sublink.univ }}  {% endif %}
 *{{ sublink.title }}*. {% if sublink.slides %}<a href="{{ sublink.slides | relative_url }}">(slides), </a>{% endif %}
{% if sublink.abstract %}{{ sublink.abstract }}{% endif %}
{% endfor %}
{% else %}
{{ link.date | date : "%A, %B %-d %Y" }}{% if link.hour != "void" %}, {{ link.hour }}{% endif %}, {{ link.where }}: **{{ link.author }}**,  
{{ link.univ }},  
*{{ link.title }}*. {% if link.slides %}<a href="{{ link.slides | relative_url }}">(slides), </a>{% endif %}
<details markdown="1">
<summary>Abstract</summary>
{% if link.abstract %}{{ link.abstract }}{% endif %}
</details>
{% endif %}

-------------------------
{% endif %}
{% endfor %}

### Past sessions
{% assign year = "3000" %}


{% for link in site.data.applied-mathematics %}
{% if link.next != "yes" %}
{% assign link_year = link.date | date : "%Y" %}
{% if link_year != year %}{% assign year = link_year %}<h3>{{ year }}</h3>{% endif %}
{% if link.sem == "scommun" %}
{{ link.date | date : "%B %-d %Y" }}{% if link.hour != "void" %}, {{ link.hour }}, {% endif %}: {{ link.where }} **{{ link.author }}**,  
{% if link.univ %}{{ link.univ }}  {% endif %}
{% if link.title %}*{{ link.title }}*.{% endif %}
{% for sublink in link.PROG %}
 - {{ sublink.hour }}: **{{ sublink.author }}**,  
 {% if sublink.univ %}{{ sublink.univ }}  {% endif %}
 *{{ sublink.title }}*. {% if sublink.slides %}<a href="{{ sublink.slides | relative_url }}">(slides), </a>{% endif %}
{% if sublink.abstract %}{{ sublink.abstract }}{% endif %}
{% endfor %}
{% else %}
{{ link.date | date : "%A, %B %-d %Y" }}{% if link.hour != "void" %}, {{ link.hour }}{% endif %}, {{ link.where }}: **{{ link.author }}**,  
{{ link.univ }},  
*{{ link.title }}*. {% if link.slides %}<a href="{{ link.slides | relative_url }}">(slides), </a>{% endif %}
<details markdown="1">
<summary>Abstract</summary>
{% if link.abstract %}{{ link.abstract }}{% endif %}
</details>
{% endif %}

-------------------------
{% endif %}
{% endfor %}


