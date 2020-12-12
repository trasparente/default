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
</details><br>

<div class='categories'>{% assign sorted_categories = site.categories | sort %}
  <strong>Categories:</strong> <a href='#'>All</a> • {% for category in sorted_categories %}<a href='#'>{{ category[0] }}</a>{% unless forloop.last %} • {% endunless %}{% endfor %}
</div>  

<div class='tags'>{% assign sorted_tags = site.tags | sort %}
  <strong>Tags:</strong> <a href='#'>All</a> • {% for tag in sorted_tags %}<a href='#'>{{ tag[0] }}</a>{% unless forloop.last %} • {% endunless %}{% endfor %}
</div>

<script>
  const cat_links = document.querySelectorAll('.categories a');
  const tag_links = document.querySelectorAll('.tags a');
  console.log(cat_links);
  console.log(tag_links);
  tag_links.forEach(link => {
    console.log(link);
    link.onclick = function serve(e) {
      e.preventDefault();
      console.log(e);
    }
  });
  tag_links.forEach(link => {
    console.log(link);
    link.onclick = function serve(e) {
      e.preventDefault();
      console.log(e);
    }
  });
</script>

{% for category in site.categories %}<div category='{{ category[0] }}'><h3>{{ category[0] }}</h3><ul>
{% for post in category[1] %}<li tags='{{ post.tags | join: " " }}'> <a href='{{ post.url | absolute_url }}'>{{ post.title }}</a> {{ post.date | date_to_string }}</li>
{% endfor %}</ul></div>
{% endfor %}
