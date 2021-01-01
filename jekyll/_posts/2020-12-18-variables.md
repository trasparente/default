---
tags: [site,page]
---
{% assign pages_list = site.pages | map: "path" | join: " " %}
{% assign static_files_list = site.static_files | map: "path" | join: " " %}
{% assign html_pages_list = site.html_pages | map: "path" | join: " " %}
{% assign html_files_list = site.html_files | map: "path" | join: " " %}

Site | Size | Details
---|---|---
pages | {{ site.pages.size }} | `{{ pages_list }}`
html_pages | {{ site.html_pages.size }} | pages subset with `.html`: `{{ html_pages_list }}`
static_files | {{ site.static_files.size }} | not processed by Jekyll/Liquid: `{{ static_files_list }}`
html_files | {{ site.html_files.size }} | static_files subset with `.html`: `{{ html_files_list }}`


Page | Value
---|---
url | `{{ page.url }}`
path | `{{ page.path }}`
id | `{{ page.id }}`
dir | `{{ page.dir }}`
name | `{{ page.name }}`

{% include footer.md %}
