---
layout: draw
title:
permalink: /15_lat/
---

<div style="text-align:left; display: flex; align-items: center;">
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="prevImage();" style="border: 0px; background-color:white;"> 
    <span class="arrowhtml">&#8249;</span> </button> 
  </div>
  <div style="flex: 0 0 40%;">
    <img class="vertical-center" id="image" src="{{ site.baseurl }}/images/15_lat/2023/overthrown.jpg" alt="ide" style="width: 80vw">
  </div>
  <div style="flex: 0 0 40%; align-items: center;">
    <p style="text-align:left;" id="subtitle"> 27/12/2023 </p>
  </div>
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="nextImage();" style="border: 0px; background-color:white;"> 
    <span class="arrowhtml">&#8250;</span> </button>
  </div>
</div>


<script>

var index      = 0;
var index_no   = 4;
var image_list = ["{{ site.baseurl }}/images/15_lat/2023/overthrown.jpg",
                  "{{ site.baseurl }}/images/15_lat/2023/czarny_pocisk.jpg",
                  "{{ site.baseurl }}/images/15_lat/2023/oddech.jpg",
                  "{{ site.baseurl }}/images/15_lat/2023/justken.jpg",
                  ]
var text_list = [ "Your faith was strong but you needed proof \n You saw her bathing on the roof \n Her beauty in the moonlight overthrew you \n She tied you to a kitchen chair \n She broke your throne, and she cut your hair \n And from your lips she drew the Hallelujah",
                  "Mówią na niego Czarny Pocisk \n On samochodem mknie \n W czyste białe światło \n Nucąc rzewną pieśń \n Nie wołaj nie zaklinaj \n Nie usłyszy nic \n Tu nie miał nigdy domu i każdy z niego drwi",
                  "Jeszcze mi głupio \n Jeszcze wstyd \n Nie jestem gotowa \n Nie przyjdą te słowa \n Znasz mnie \n Chyba gdzieś głębiej muszę zejść \n Cała się trzęsę jest mi źle \n Bałagan mam w głowie \n Nie myślę rozsądnie",
                  "I'm just Ken (and I'm enough) \n And I'm great at doing stuff \n So, hey, check me out, yeah, I'm just Ken \n My name's Ken (and so am I) \n Put that manly hand in mine \n So, hey, world, check me out, yeah, I'm just Ken \n",
                  ]

function formatTextWithLineBreaks(text) {
    return text.replace(/\n/g, "<br>");
}

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
  img.src       = image_list[index];
  txt.innerHTML = formatTextWithLineBreaks(text_list[index]);
  return false;
}

function nextImage()
{
  var img = document.getElementById("image");
  var txt = document.getElementById("subtitle");
  index = (index + 1) % index_no;
  img.src         = image_list[index];
  txt.innerHTML = formatTextWithLineBreaks(text_list[index]);
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
