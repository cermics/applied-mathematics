---
layout: page
title: "Applied Mathematics Seminar: previous years"
permalink: /previous-years/
cover-img: /assets/images/coriolis-reunion.jpg
---

Back to the [current seminars]({{ '/' | relative_url }}).

{% assign this_year = site.time | date: "%Y" | plus: 0 %}
{% assign days = site.data.applied-mathematics | group_by_exp: "link", "link.date | date: '%Y-%m-%d'" | sort: "name" %}
{% assign year = "3000" %}

{% for day in days reversed %}{% for link in day.items %}
{% assign link_year = link.date | date: "%Y" %}
{% assign link_year_num = link_year | plus: 0 %}
{% if link.next != "yes" and link_year_num < this_year %}
{% if link_year != year %}{% assign year = link_year %}<h3>{{ year }}</h3>{% endif %}
{% include seminar.html link=link %}
{% endif %}
{% endfor %}{% endfor %}
