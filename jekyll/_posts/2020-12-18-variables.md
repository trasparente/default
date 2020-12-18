---
tags: [site,page]
---
Site | Size |
---|---|
pages | {{ site.pages.size }}
html_pages | pages subset with `.html` {{ site.html_pages.size }}
static_files | not processed by Jekyll/Liquid {{ site.static_files.size }}
html_files | static_files subset with `.html` {{ site.html_files.size }}

Page ||
---|---|
url | {{ page.url }}
path | {{ page.path }}
id | {{ page.id }}
dir | {{ page.dir }}
name | {{ page.name }}
