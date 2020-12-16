<br>

[Repo]({{ site.github.repository_url }}) | [Page]({{ site.github.repository_url }}/blob/main/{{ page.path }}) | {{ site.posts | size }} Posts | {{ site.categories | size }} Categories | {{ site.tags | size }} Tags | {% assign start = '2020-12-10' | date: '%s' %}{% assign difference = site.time | date: '%s' | minus: start %}{{ difference | divided_by: 86400 | round: 1 }} Days old | {{ site.time }}
