---
layout:
title:
permalink: /uwagaide/
---

<div style="text-align:center; display: flex; margin-left: 50px">
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="prevImage();" style="border: 0px; background-color:white;"> <span class="arrowhtml">&#8249;</span> </button> </div>
  <div style="flex: 0 0 80%;"><img class="vertical-center" id="image" src="{{ site.baseurl }}/images/lara_1a.gif" alt="ide" style="height: 100vh"></div>
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="nextImage();" style="border: 0px; background-color:white;"> <span class="arrowhtml">&#8250;</span> </button></div>
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
  border-width: 0 6px 6px 0;
  display: inline-block;
  padding: 6px;
}

.arrowhtml {
  color: black;
  font-size: 7vh;
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
  margin: auto;
  display: flex;
  position: absolute;
  border-width: 0px;
  background-color: white;
}

.arrowhtml:hover {
    color: red;
    font-size: 7vh;
  }

</style>
