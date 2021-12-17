---
layout: page
title: grafika
permalink: /grafika/
---

szkice szkice

### momenty

#### Camille przy barze

<img src="{{ site.baseurl }}/images/camille.gif" onclick="toggle()" alt="Camille" style="width: 350px;"/>
<img src="{{ site.baseurl }}/images/camille2.gif" alt="Camille2" style="width: 350px;"/>

####  doktor Rieux patrzy przez okno

<img src="{{ site.baseurl }}/images/rieux_short.gif" alt="rieux" style="width: 500px;"/>

####  Le Jeune Homme et la Mort

<img src="{{ site.baseurl }}/images/bary_bw.gif" alt="barybw" style="width: 500px;"/>
<img src="{{ site.baseurl }}/images/bary_cf.gif" alt="barycf" style="width: 500px;"/>

####  siatkarskie koszulki

<img
  src="{{ site.baseurl }}/images/siatka/s_attacker_c.jpg"
  alt="attacker"
  style="width: 170px;"
  onmouseover="this.src='{{ site.baseurl }}/images/siatka/s_attacker.jpg';"
  onmouseout="this.src='{{ site.baseurl }}/images/siatka/s_attacker_c.jpg';"
/>
<img
  src="{{ site.baseurl }}/images/siatka/s_setter_c.jpg"
  alt="setter"
  style="width: 175px;"
  onmouseover="this.src='{{ site.baseurl }}/images/siatka/s_setter.jpg';"
  onmouseout="this.src='{{ site.baseurl }}/images/siatka/s_setter_c.jpg';"
/>
<img
  src="{{ site.baseurl }}/images/siatka/s_fire_c.jpg"
  alt="fire"
  style="width: 170px;"
  onmouseover="this.src='{{ site.baseurl }}/images/siatka/s_fire.jpg';"
  onmouseout="this.src='{{ site.baseurl }}/images/siatka/s_fire_c.jpg';"
/>
<img
  src="{{ site.baseurl }}/images/siatka/s_libero_c.jpg"
  alt="libero"
  style="width: 175px;"
  onmouseover="this.src='{{ site.baseurl }}/images/siatka/s_libero.jpg';"
  onmouseout="this.src='{{ site.baseurl }}/images/siatka/s_libero_c.jpg';"
/>

####  krypto kubki

<img src="{{ site.baseurl }}/images/kubki/adam_c.png" onclick="toggleadam()" alt="adam" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/aneta_c.png" onclick="toggleaneta()" alt="aneta" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/daniel_c.png" onclick="toggledaniel()" alt="daniel" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/dorota_c.png" onclick="toggledorota()" alt="dorota" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/krzysiek_c.png" onclick="togglek()" alt="krzysiek" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/michal_c.png" onclick="togglem()" alt="michal" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/wladek_c.png" onclick="togglewladek()" alt="wladek" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/pawel_c.png" onclick="togglepawel()" alt="pawel" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/maciek_c.png" onclick="togglemaciek()" alt="maciek" style="width: 170px;" />

####  encepence

<img src="{{ site.baseurl }}/images/encepence/trilab.jpg" alt="trilab" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/encepence/orzel.jpg" alt="orzel" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/encepence/tritor.jpg" alt="trirot" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/encepence/donpedro.jpg" alt="donpedro" style="width: 170px;" />

#### Identyfikacja wizualna Eksperymentalnej Platrformy Walidacyjnej (EPW)

####  [logo EPW - etap 1](https://keipie.github.io/epw/)

####  [logo EPW - etap 2](https://keipie.github.io/epw2/)

####  [identyfikcja EPW finalna](https://keipie.github.io/epw-identyfikacja-fin/)

#### szepty

<img src="{{ site.baseurl }}/images/szeptucha-cr.svg" class="rotate" alt="szept" style="width: 200px;" />

### napisz

[aleksandra.horubala@gmail.com](mailto:aleksandra.horubala@gmail.com)

<audio
  id="audio"
  src="{{ site.baseurl }}/audio/ringoffireburdon.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audioadam"
  src="{{ site.baseurl }}/audio/atlantyda.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audioaneta"
  src="{{ site.baseurl }}/audio/herkules.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audiodaniel"
  src="{{ site.baseurl }}/audio/onemorecup.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audiodorota"
  src="{{ site.baseurl }}/audio/bts.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audiok"
  src="{{ site.baseurl }}/audio/automaty.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audiom"
  src="{{ site.baseurl }}/audio/riders.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audiowladek"
  src="{{ site.baseurl }}/audio/donpedro.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audiopawel"
  src="{{ site.baseurl }}/audio/psy.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<audio
  id="audiomaciek"
  src="{{ site.baseurl }}/audio/odchodzac.mp3">
  Your browser does not support the
  <code>audio</code> element.
</audio>

<script>
  var play = false;
  var toggle = function () {
    if (play) {
      document.getElementById('audio').pause()
    } else {
      document.getElementById('audio').currentTime = 27.5
      document.getElementById('audio').play()      
    }
    play = !play
  }
  var toggleadam = function () {
    if (play) {
      document.getElementById('audioadam').pause()
    } else {
      document.getElementById('audioadam').currentTime = 44
      document.getElementById('audioadam').play()      
    }
    play = !play
  }
  var toggleaneta = function () {
    if (play) {
      document.getElementById('audioaneta').pause()
    } else {
      document.getElementById('audioaneta').currentTime = 21
      document.getElementById('audioaneta').play()      
    }
    play = !play
  }
  var toggledaniel = function () {
    if (play) {
      document.getElementById('audiodaniel').pause()
    } else {
      document.getElementById('audiodaniel').currentTime = 65
      document.getElementById('audiodaniel').play()      
    }
    play = !play
  }  
  var toggledorota = function () {
    if (play) {
      document.getElementById('audiodorota').pause()
    } else {
      document.getElementById('audiodorota').currentTime = 8
      document.getElementById('audiodorota').play()      
    }
    play = !play
  }
  var togglek = function () {
    if (play) {
      document.getElementById('audiok').pause()
    } else {
      document.getElementById('audiok').currentTime = 23
      document.getElementById('audiok').play()      
    }
    play = !play
  }
  var togglem = function () {
    if (play) {
      document.getElementById('audiom').pause()
    } else {
      document.getElementById('audiom').currentTime = 47
      document.getElementById('audiom').play()      
    }
    play = !play
  }
  var togglewladek = function () {
    if (play) {
      document.getElementById('audiowladek').pause()
    } else {
      document.getElementById('audiowladek').currentTime = 28
      document.getElementById('audiowladek').play()      
    }
    play = !play
  }
  var togglepawel = function () {
    if (play) {
      document.getElementById('audiopawel').pause()
    } else {
      document.getElementById('audiopawel').currentTime = 0
      document.getElementById('audiopawel').play()      
    }
    play = !play
  }
  var togglemaciek = function () {
    if (play) {
      document.getElementById('audiomaciek').pause()
    } else {
      document.getElementById('audiomaciek').currentTime = 55
      document.getElementById('audiomaciek').play()      
    }
    play = !play
  }

</script>
