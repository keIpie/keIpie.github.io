---
layout: page
title: grafika
permalink: /grafika/
---

mój świat twój świat

### a mon seul desir
- Camille przy barze

<img src="{{ site.baseurl }}/images/camille.gif" onclick="toggle()" alt="Camille" style="width: 350px;"/>
<img src="{{ site.baseurl }}/images/camille2.gif" alt="Camille2" style="width: 350px;"/>

- doktor Rieux patrzy przez okno

- siatkarskie koszulki

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

- krypto kubki

<img src="{{ site.baseurl }}/images/kubki/adam_c.png" alt="adam" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/aneta_c.png" alt="aneta" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/daniel_c.png" alt="daniel" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/dorota_c.png" onclick="toggledorota()" alt="dorota" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/krzysiek_c.png" onclick="togglek()" alt="krzysiek" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/michal_c.png" onclick="togglem()" alt="michal" style="width: 170px;" />

<audio
  id="audio"
  src="{{ site.baseurl }}/audio/ringoffireburdon.mp3">
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
  var toggledorota = function () {
    if (play) {
      document.getElementById('audiodorota').pause()
    } else {
      document.getElementById('audiodorota').currentTime = 7
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
</script>

### napisz

[aleksandra.horubala@gmail.com](mailto:aleksandra.horubala@gmail.com)
