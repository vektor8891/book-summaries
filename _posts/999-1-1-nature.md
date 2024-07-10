---
layout: post
title: "TERMÉSZET / NATURE"
published: true
---

* TOC
{:toc}

{% assign kingdom = "" %}
{% assign type = "" %}

{% for row in site.data.nature %}

<!-- kingdom -->
{% if row["_kingdom"] != kingdom %}
{% assign kingdom = row["_kingdom"] %}
{% assign type = "aaa" %}

## {{ kingdom }}

{% if kingdom == "Plantae" %}
🇺🇸 plant kingdom / 🇭🇺 növények országa
{% endif %}
{% if kingdom == "Animalia" %}
🇺🇸 animal kingdom / 🇭🇺 állatok országa
{% endif %}
{% endif %}

<!-- type -->
{% if row["type"] != type %}
{% assign type = row["type"] %}

### {{ type }}

{% if type == "Lignosae" %}
🇺🇸 woody plants / 🇭🇺 fás szárúak
{% endif %}
{% if type == "Herbaceaes" %}
🇺🇸 herbaceous plants / 🇭🇺 lágyszárúak
{% endif %}
{% if type == "Insecta" %}
🇺🇸 insects / 🇭🇺 rovarok
{% endif %}
{% endif %}

<!-- details -->
#### {{ row["lat"] }}

🇺🇸 {{ row["eng"] }} / 🇭🇺 {{ row["hun"] }}

([Source]({{ row["source"] }}){:target="_blank" rel="noopener noreferrer"}) {{ row["notes"] }}

{% assign urls = row["urls"] | split: "|" %}

{% for url in urls %}
![{{ row["lat"] }}]({{ url }})
<!-- {{ url }} -->
{% endfor %}

{% endfor %}
