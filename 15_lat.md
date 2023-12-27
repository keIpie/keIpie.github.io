---
layout: draw
title:
permalink: /15_lat/
---

<div style="text-align:center; display: flex;">
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="prevImage();" style="border: 0px; background-color:white;"> 
    <span class="arrowhtml">&#8249;</span> </button> 
  </div>
  <div style="flex: 0 0 40%;">
    <img class="vertical-center" id="image" src="{{ site.baseurl }}/images/muzyka/1.jpg" alt="ide" style="width: 80vw">
  </div>
  <div style="flex: 0 0 40%;">
    <p style="text-align:center" id="subtitle"> małe preludia </p>
  </div>
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="nextImage();" style="border: 0px; background-color:white;"> 
    <span class="arrowhtml">&#8250;</span> </button>
  </div>
</div>


<script>

var index      = 0;
var index_no   = 2;
var image_list = ["{{ site.baseurl }}/images/muzyka/1.jpg",
                  "{{ site.baseurl }}/images/muzyka/2.JPG",
                  ]
var text_list = [ "małe preludia <br> małe preludia <br> małe preludia",
                  "zgrzyt",
                  ]

function prevImage()
{
  var img = document.getElementById("image");
  var txt = document.getElementById("subtitle");
  if (index != 0) {
    index = (index - 1) % index_no;
  }
  else {
    index = index_no - 1;
  }
  img.src         = image_list[index];
  txt.textContent = text_list[index];
  return false;
}

function nextImage()
{
  var img = document.getElementById("image");
  var txt = document.getElementById("subtitle");
  index = (index + 1) % index_no;
  img.src         = image_list[index];
  txt.textContent = text_list[index];
  return false;
}

</script>


<style>

.arrowhtml {
  color: black;
  font-size: 7vh;
}

.vertical-center {
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  border-width: 0px;
  background-color: white;
}

.arrowhtml:hover {
    color: red;
    font-size: 7vh;
  }

</style>
