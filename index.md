---
---
<details>
  <summary>Add</summary>
  <script>
    function editor(){
      const category = document.getElementById('category').value.toLowerCase().replace(/[^a-zA-Z0-9]+/g,'-');
      const date = "{{ site.time | date: '%Y-%m-%d-' }}";
      const title = document.getElementById('title').value.toLowerCase().replace(/[^a-zA-Z0-9]+/g,'-');
      const tags = document.getElementById('tags').value;
      const url='{{ site.github.repository_url }}/new/main?filename=' + category + '/_posts/' + date + title + '.md&value=---%0Atags:%20[' + tags + ']%0A---%0A';
      location = url;
      return true
    };
  </script>
  <input id=title placeholder=Title required>
  <input id=category placeholder=Category required>
  <input id=tags placeholder=Tags>
  <button onclick='editor()'>Editor</button>
</details>

{% for category in site.categories %}<div category='{{ category[0] }}'><h3>{{ category[0] }}</h3><ul>
{% for post in category[1] %}<li tags='{{ page.tags | join: " " }}' markdown='1'> [{{ post.title }}]({{ post.url | absolute_url }}) {{ post.date | date_to_string }}</li>
{% endfor %}</ul></div>
{% endfor %}
