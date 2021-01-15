---
permalink: /papers/
layout: single
title: Papers
toc: false
---

{% assign hashes = site.data.papers %}
{% capture years %}
{% for hash in hashes %}
{{ hash[0] }}
{% endfor %}
{% endcapture %}

{% assign sortedyears = years | split:' ' | sort | reverse %}
{% for year in sortedyears %}
### {{ year | replace: "_", " - " }}
{% assign selected = hashes[year] | where: "selected", "y" %}
{% for paper in selected %}
{% include paper.html paper=paper %}
{% endfor %}
{% endfor %}


