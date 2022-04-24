---
layout:
title:
permalink: /elementy/
---

<div style="text-align:center; display: flex; margin-left: 50px">
  <div style="flex: 0 0 10%;"><button class="vertical-center" onclick="prevImage();"> <i class="arrow left"></i> </button></div>
  <div style="flex: 0 0 80%;"><img class="vertical-center" id="image" src="{{ site.baseurl }}/images/fala_a.gif" alt="ide" style="width: 500px; margin-top: 100px;"></div>
  <div style="flex: 0 0 10%;"><button class="vertical-center" onclick="nextImage();"> <i class="arrow right"></i> </button></div>
</div>


<script>

var index      = 0;
var index_no   = 2;
var image_list = ["{{ site.baseurl }}/images/fala_a.gif", "{{ site.baseurl }}/images/salome.GIF"]

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

.arrow {
  border: solid black;
  border-width: 0 6px 6px 0;
  display: inline-block;
  padding: 6px;
}

.right {
  transform: rotate(-45deg);
  -webkit-transform: rotate(-45deg);
}

.left {
  transform: rotate(135deg);
  -webkit-transform: rotate(135deg);
}

.vertical-center {
  margin: 0;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
  border-width: 0px;
  background-color: white;
}

.arrow:hover {
    border: solid red;
  }

</style>
