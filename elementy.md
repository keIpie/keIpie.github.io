---
layout:
title:
permalink: /elementy/
---

<div style="text-align:center; display: flex; margin-left: 50px">
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="prevImage();"> <i class="arrow left"></i> </button></div>
  <div style="flex: 0 0 80%;"><img class="vertical-center" id="image" src="{{ site.baseurl }}/images/fala_a.gif" style="height: 100vh" alt="ide"></div>
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="nextImage();"> <i class="arrow right"></i> </button></div>
</div>


<script>

var index      = 0;
var index_no   = 2;
var image_list = ["{{ site.baseurl }}/images/fala_a.gif", "{{ site.baseurl }}/images/salome_cut.gif"]

function prevImage()
{
  var img = document.getElementById("image");
  if (index != 0) {
    index = (index - 1) % index_no;
  }
  else {
    index = index_no - 1;
  }
  img.src = image_list[index];
  return false;
}

function nextImage()
{
  var img = document.getElementById("image");
  index = (index + 1) % index_no;
  img.src = image_list[index];
  return false;
}

</script>


<style>

.plain-button {
  color: black;
  border-width: 0px;
  background-color: white;
}

.vertical-center {
  margin: auto;
  display: flex;
  align-items: center;
  border-width: 0px;
  background-color: white;
}

.plain-button:hover {
    color: red;
  }

</style>
