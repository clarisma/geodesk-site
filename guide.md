---
layout: guide
title: GeoDesk Developers' Guide
next: intro-to-osm.md
---
# GeoDesk Developer's Guide

Impatient? Read the [Five-minute tutorial](tutorial).

<div class="box todo" markdown="1">
GeoDesk is **Pre-Release**. Some capabilities may be unavailable in Version {{ site.geodesk_version}}.<br>API and implementation subject to change.
</div>

{% assign next_page_name = page.next %} 

{% for i in (1..100) %}
    {% if next_page_name == "" %}
        {% break %}
    {% else %}
        {% assign next_page = site.pages | where: "name", next_page_name | first %}
<p><a href="{{ next_page.url | remove: ".html" }}">{{ next_page.title }}</a>
        {% assign next_page_name = next_page.next %}
    {% endif %}
{% endfor %}




