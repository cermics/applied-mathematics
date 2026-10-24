---
layout: page
cover-img: /assets/images/coriolis-reunion.jpg
---


Organizers: <a href="https://thebiglouloup.github.io/loucaspillaudvivien/">Loucas Pillaud-Vivien</a>,
<a href="https://lauragrazioli.github.io/">Laura Grazioli</a>.

See the <a href="https://calendar.google.com/calendar/embed?src=5e375da2e8afa22df729e4f6a1467993b104b67e8f44a4e6839d8dc1eba59524%40group.calendar.google.com&amp;ctz=Europe%2FParis">Google Agenda of the seminar</a>, and add the <a href="https://calendar.google.com/calendar/ical/5e375da2e8afa22df729e4f6a1467993b104b67e8f44a4e6839d8dc1eba59524%40group.calendar.google.com/public/basic.ics">iCal url</a> to your calendar.

{% comment %}Seminars grouped by day and sorted chronologically, whatever their order in the data file.{% endcomment %}
{% assign this_year = site.time | date: "%Y" | plus: 0 %}
{% assign days = site.data.applied-mathematics | group_by_exp: "link", "link.date | date: '%Y-%m-%d'" | sort: "name" %}

### Upcoming seminars

{% for day in days %}{% for link in day.items %}
{% if link.next == "yes" %}
{% include seminar.html link=link %}
{% endif %}
{% endfor %}{% endfor %}

### Past sessions in {{ this_year }}

{% for day in days reversed %}{% for link in day.items %}
{% assign link_year = link.date | date: "%Y" | plus: 0 %}
{% if link.next != "yes" and link_year == this_year %}
{% include seminar.html link=link %}
{% endif %}
{% endfor %}{% endfor %}

See the [seminars from previous years]({{ '/previous-years/' | relative_url }}).
