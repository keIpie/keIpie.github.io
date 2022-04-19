---
layout:
title:
permalink: /uwagaide/
---

<div style="text-align:center; display: inline-block; margin-left: 50px">
  <button class="vertical-center" onclick="prevImage();"> <i class="arrow left"></i> </button>
  <img id="image" src="{{ site.baseurl }}/images/lara_1_crop.gif" alt="ide" style="width: 1600px; margin-top: 100px;" />
  <button class="vertical-center" onclick="nextImage();"> <i class="arrow right"></i> </button>
</div>


<script>

var index      = 0;
var index_no   = 2;
var image_list = ["{{ site.baseurl }}/images/lara_1a.gif", "{{ site.baseurl }}/images/lara_2a.gif"]

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
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 3px;
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

.vertical-center:hover {
      background-color: yellow;
  }

</style>
