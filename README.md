# default
Default notes

<details>
  <summary>Add</summary>
  <input id=title placeholder=title>
  <input id=tags placeholder=tags>
  <button onclick="const url='{{ site.github.repository_url }}/new/main?title={{ site.time | date: '%Y-%m-%d-' }}'+document.getElementById('title').value+'.md&value=---%0Atags:%20['+document.getElementById('tags').value.split(',')+']%0A---%0A'; console.log(url)">Editor</button>
</details>
