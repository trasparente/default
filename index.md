---
---
<details>
  <summary>Add</summary>
  <form id='add'>
    <input id=add_title placeholder=Title required>
    <input id=add_category placeholder=Category required>
    <select name="add_category" id="add_category">
      {% assign sorted_categories = site.categories | sort %}{% for category in sorted_categories %}<option value="{{ category[0] }}">{{ category[0] }} ({{ category[1] | size }})</option>{% endfor %}
    </select>
    <input id=add_tags placeholder=Tags>
    <input type=submit value=Editor>
  </form>
    <script>
    document.getElementById('add').onsubmit = (event) => {
      event.preventDefault();
      const category = document.getElementById('add_category').value.toLowerCase().replace(/[^a-zA-Z0-9]+/g,'-');
      const date = "{{ site.time | date: '%Y-%m-%d-' }}";
      const title = document.getElementById('add_title').value.toLowerCase().replace(/[^a-zA-Z0-9]+/g,'-');
      const tags = document.getElementById('add_tags').value;
      const url='{{ site.github.repository_url }}/new/main?filename=' + category + '/_posts/' + date + title + '.md&value=---%0Atags:%20[' + tags + ']%0A---%0A';
      location = url;
      return true
    };
  </script>
</details>
<p></p>

Category <select name="category" id="category">
    <option value="all">All</option>
    {% assign sorted_categories = site.categories | sort %}{% for category in sorted_categories %}<option value="{{ category[0] }}">{{ category[0] }} ({{ category[1] | size }})</option>{% endfor %}
</select>

Tag <select name="tag" id="tag">
    <option value="all">All</option>
    {% assign sorted_tags = site.tags | sort %}{% for tag in sorted_tags %}<option value="{{ tag[0] }}">{{ tag[0] }} ({{ tag[1] | size }})</option>{% endfor %}
</select>

<script>
  document.querySelectorAll('#category, #tag').forEach(select => {
    select.onchange = (e) => {
      const value = e.target.value;
      const id = e.target.id;
      if (value == 'all') {
        document.querySelectorAll('[' + id + ']').forEach(el => el.style.display = 'revert');
      } else {
        document.querySelectorAll('[' + id + ']').forEach(el => el.style.display = 'none');
        document.querySelectorAll('[' + id + '="' + value + '"]').forEach(el => el.style.display = 'revert')
      }
    }
  });
</script>

{% for category in site.categories %}<div category='{{ category[0] }}' tag='{{ category[1] | map: "tags" | join: " " }}'><h3>{{ category[0] }}</h3><ul>
{% for post in category[1] %}<li tag='{{ post.tags | join: " " }}'> <a href='{{ post.url | absolute_url }}'>{{ post.title }}</a> {{ post.date | date_to_string }}</li>
{% endfor %}</ul></div>
{% endfor %}

{% include footer.md %}
