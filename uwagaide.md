---
layout: draw
title:
permalink: /uwagaide/
---

<div style="text-align:center; display: flex;">
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="prevImage();" style="border: 0px; background-color:white;"> <span class="arrowhtml">&#8249;</span> </button> </div>
  <div style="flex: 0 0 80%;"><img class="vertical-center" id="image" src="{{ site.baseurl }}/images/lara/lara_zasada_1.mp4" alt="ide" style="width: 80vw"></div>
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="nextImage();" style="border: 0px; background-color:white;"> <span class="arrowhtml">&#8250;</span> </button></div>
</div>


<script>

var index      = 0;
var index_no   = 9;
var image_list = ["{{ site.baseurl }}/images/lara/lara_zasada_1.mp4",
                  "{{ site.baseurl }}/images/lara/lara_zasada_2.mp4",
                  "{{ site.baseurl }}/images/lara/lara_zasada_3.mp4",
                  "{{ site.baseurl }}/images/lara/lara_zasada_4.mp4",
                  "{{ site.baseurl }}/images/lara/lara_zasada_5.mp4",
                  "{{ site.baseurl }}/images/lara/lara_zasada_6.mp4",
                  "{{ site.baseurl }}/images/lara/lara_zasada_7.mp4",
                  "{{ site.baseurl }}/images/lara/lara_zasada_8.mp4",
                  "{{ site.baseurl }}/images/lara/lara_zasada_9.mp4",
                  ]

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
