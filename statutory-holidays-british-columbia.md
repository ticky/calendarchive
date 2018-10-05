---
title: Statutory Holidays in British Columbia
description: Calendar of Statutory Holidays in British Columbia, Canada
---

Calendar of Statutory Holidays in British Columbia, Canada

[Subscribe](webcal:{{ site.url | replace: 'http:', '' | replace: 'https:', '' }}{{ site.baseurl }}{% link statutory-holidays-british-columbia.ics %})

## Events

{% assign now = 'now' | date: '%s' | plus: 0 %}
{% assign calendar = site.collections | where: "label", "statutory_holidays_british_columbia" | first %}
{% assign events = calendar.docs %}

{% for event in events %}
{% assign date = event.date | date: '%s' | plus: 0 %}
{% if date >= now %}
- **{{ event.title }}**, {% if event.all_day %}{{ event.date | date: "%A %e %B %Y" }}{% else %}{{ event.date | date: "%A %e %B %Y, %H:%M" }}{% endif %}
{% endif %}
{% endfor %}
