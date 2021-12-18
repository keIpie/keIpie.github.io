---
layout: page
title:
permalink: /szepty/
---

<div style="text-align:center"><img src="{{ site.baseurl }}/images/szeptucha-cr.svg" class="rotate" onclick="rotszept(this)" alt="szept" style="width: 200px;" /></div>
<div style="text-align:center"><img src="{{ site.baseurl }}/images/sz-napis.png" alt="szeptu" style="width: 250px;" /></div>
<br><br><br>
<button id="button_r">random</button>
<input type="file" id="inputfile" />
<input id="cols" type="number" />
<br><br>
<pre id="output"></pre>
<div id="table"></div>

<style>

table {
  margin-left: auto;
  margin-right: auto;
}

td {
  width: 15px;
  height: 15px;
}
.white {
  background: white;
}
.black {
  background: black;
}

</style>

<script>

let cols = 10;
let rows = 20;
let bitstring = "101001001010010101001001010010011111111100101010010101000000010101010010101001010101001010010000000000000110000000000000000011010010010100101000000000001100101010010100101000111111111111100100101010011111110101001010101001000000010101001010000000000000000110010010010111111010010010101010010101001111111001010100101001000000001100101001001001111010100101001000101010010100101000100001111100101110010100101100101010100101001010101001001010100101000000000000000000000000010100100101111111111111010010100100101001000001111111111111110010100100101001010010011111000101010000011111110010101"

document.getElementById("cols").addEventListener("change", () => {
    cols = document.getElementById("cols").value;
    resize();
})

document.getElementById("button_r").addEventListener("click", () => {
    cols = document.getElementById("cols").value;
    rows = 100;
    refresh();
})

document.getElementById('inputfile').addEventListener('change', function() {
    var fr=new FileReader();
    fr.onload=function(){
      bitstring = fr.result;
      }        
    fr.readAsText(this.files[0]);
})

function resize() {
  let table = '<table>';
  let rows = bitstring.length/cols
  for (let i = 0; i < rows; i++) {
    table += '<tr>'
    for (let j = 0; j < cols; j++) {
      if (bitstring[i*cols+j] == 1) {
        table += '<td class="black"></td>'
      } else {
        table += '<td class="white"></td>'
      }
    }
    table += '</tr>'
  }
  table += '</table>'
  document.getElementById("table").innerHTML = table;  
}

function refresh() {
  let table = '<table>';
  let bitstring = ""
  for (let i = 0; i < rows; i++) {
    table += '<tr>'
    for (let j = 0; j < cols; j++) {
      if (Math.random() < 0.5) {
        table    += '<td class="white"></td>'
        bitstring += "0"
      } else {
        table += '<td class="black"></td>'
        bitstring += "1"
      }
    }
    table += '</tr>'
  }
  table += '</table>'
  document.getElementById("table").innerHTML = table;  
}

</script>
