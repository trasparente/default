# default
Default notes

<details>
  <summary>Add</summary>
  <input id=title placeholder=title required>
  <input id=category placeholder=category required>
  <input id=tags placeholder=tags>
  <button onclick="go_to_edit()">Editor</button>
  <script>
    function go_to_edit(){
      const category = document.getElementById('category');
      const date = {{ site.time | date: '%Y-%m-%d-' }};
      const title = document.getElementById('title').value.toLowerCase().replace /[^a-zA-Z0-9]+/g,'-';
      const tags = document.getElementById('tags').value;
      const url='{{ site.github.repository_url }}/new/main?filename=' + category + '/_posts/' + date + title + '.md&value=---%0Atags:%20[' + tags + ']%0A---%0A';
      return console.log(url);
    };
  </script>
</details>
