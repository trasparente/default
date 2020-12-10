# default
Default notes

<details>
  <summary>Add</summary>
  <input id=title placeholder=title>
  <input id=tags placeholder=tags>
  <button onclick="const url='{{ site.github.repository_url }}/new/main?title={{ site.time | date: '%Y-%m-%d-' }}'+document.getElementById('title').value; console.log(url)">Editor</button>
</details>
