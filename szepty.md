---
layout: page
title: szepty
permalink: /szepty/
---

<div style="text-align:center"><img src="{{ site.baseurl }}/images/szeptucha-cr.svg" class="rotate" onclick="rotszept(this)" alt="szept" style="width: 200px;" /></div>
<div style="text-align:center"><img src="{{ site.baseurl }}/images/sz-napis.png" alt="szeptu" style="width: 250px;" /></div>


<div id="table"></div>

<script>

let table = '<table>';

for (let i = 0; i < 10; i++) {
  table += '<tr>'
  for (let j = 0; j < 20; j++) {
    if (Math.rand() < 0.5) {
      table += '<td class="white"></td>'
    } else {
      table += '<td class="black"></td>'
    }
  }
  table += '</tr>'
}

table += '</table>'

document.getElementById("table").innerHTML = table;
</script>
