---
tags: [site,page]
---
{% assign static_files_list = site.static_files | map: "path" %}
{% assign html_pages_list = site.html_pages | map: "path" %}
{% assign html_files_list = site.html_files | map: "path" %}

Site | Size | Details
---|---|---
pages | {{ site.pages.size }}
html_pages | {{ site.html_pages.size }} | pages subset with `.html` {{ html_pages_list }}
static_files | {{ site.static_files.size }} | not processed by Jekyll/Liquid {{ static_files_list }}
html_files | {{ site.html_files.size }} | static_files subset with `.html` {{ html_files_list }}

Page ||
---|---|
url | {{ page.url }}
path | {{ page.path }}
id | {{ page.id }}
dir | {{ page.dir }}
name | {{ page.name }}
