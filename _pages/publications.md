---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

This list is generated automatically from my [CV]({{ "/files/cv_killeen.pdf" | relative_url }}); see also my <a href="{{ author.googlescholar }}">Google Scholar profile</a> for citation counts.
{: .notice--info}

{% assign pubs = site.data.publications | where_exp: "p", "p.type != 'patent'" %}
{% assign years = pubs | map: "year" | uniq | sort | reverse %}
{% for year in years %}
<h2 class="pub-year">{{ year }}</h2>
{% assign items = pubs | where: "year", year %}
{% for pub in items %}{% include publication-card.html pub=pub %}{% endfor %}
{% endfor %}

{% assign patents = site.data.publications | where: "type", "patent" %}
{% if patents.size > 0 %}
<h2 class="pub-section-title">Patents</h2>
{% for pub in patents %}{% include publication-card.html pub=pub %}{% endfor %}
{% endif %}
