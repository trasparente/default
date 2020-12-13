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
  <form onsubmit='editor()'>
    <input id=title placeholder=Title required>
    <input id=category placeholder=Category required>
    <input id=tags placeholder=Tags>
    <input type=submit value=Editor>
  </form>
</details>
<p></p><select name="category" id="category">
    <option value="all">All</option>
    {% assign sorted_categories = site.categories | sort %}{% for category in sorted_categories %}<option value="{{ category[0] }}">{{ category[0] }} ({{ category[1] | size }})</option>{% endfor %}
</select>
<select name="tag" id="tag">
    <option value="all">All</option>
    {% assign sorted_tags = site.tags | sort %}{% for tag in sorted_tags %}<option value="{{ tag[0] }}">{{ tag[0] }} ({{ tag[1] | size }})</option>{% endfor %}
</select><script>
  document.querySelectorAll('select').forEach(select => {
    select.onchange = (e) => {
      const value = e.target.value;
      const id = e.target.id;
      if (value == 'all') {
        document.querySelectorAll('[' + id +']').forEach(el => el.style.display = 'revert');
      } else {
        document.querySelectorAll('[' + id +']').forEach(el => el.style.display = 'none');
        document.querySelectorAll('[' + id +'="' + value + '"]').forEach(el => el.style.display = 'revert')
      }
    }
  });
</script>

{% for category in site.categories %}<div category='{{ category[0] }}' tags='{{ category[1] | map: "tags" | join: " " }}'><h3>{{ category[0] }}</h3><ul>
{% for post in category[1] %}<li tag='{{ post.tags | join: " " }}'> <a href='{{ post.url | absolute_url }}'>{{ post.title }}</a> {{ post.date | date_to_string }}</li>
{% endfor %}</ul></div>
{% endfor %}

{% include footer.md %}
