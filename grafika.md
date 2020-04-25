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
  src="{{ site.baseurl }}/images/s_attacker_c.jpg"
  alt="attacker"
  style="width: 170px;"
  onmouseover="this.src='{{ site.baseurl }}/images/s_attacker.jpg';"
  onmouseout="this.src='{{ site.baseurl }}/images/s_attacker_c.jpg';"
/>
<img
  src="{{ site.baseurl }}/images/s_setter_c.jpg"
  alt="setter"
  style="width: 175px;"
  onmouseover="this.src='{{ site.baseurl }}/images/s_setter.jpg';"
  onmouseout="this.src='{{ site.baseurl }}/images/s_setter_c.jpg';"
/>
<img
  src="{{ site.baseurl }}/images/s_fire_c.jpg"
  alt="fire"
  style="width: 170px;"
  onmouseover="this.src='{{ site.baseurl }}/images/s_fire.jpg';"
  onmouseout="this.src='{{ site.baseurl }}/images/s_fire_c.jpg';"
/>
<img
  src="{{ site.baseurl }}/images/s_libero_c.jpg"
  alt="libero"
  style="width: 175px;"
  onmouseover="this.src='{{ site.baseurl }}/images/s_libero.jpg';"
  onmouseout="this.src='{{ site.baseurl }}/images/s_libero_c.jpg';"
/>

- krypto kubki

<img src="{{ site.baseurl }}/images/kubki/k_aneta.jpg" alt="aneta" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/k_adam.jpg" alt="adam" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/k_daniel.jpg" alt="daniel" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/k_dorota.jpg" alt="dorota" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/k_krzysiek.jpg" alt="krzysiek" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/k_michal.jpg" alt="michal" style="width: 170px;" />
<img src="{{ site.baseurl }}/images/kubki/k_next.jpg" alt="next" style="width: 170px;" />

<audio
  id="audio"
  src="{{ site.baseurl }}/audio/ringoffireburdon.mp3">
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
    console.log(play)
  }  
</script>

### napisz

[aleksandra.horubala@gmail.com](mailto:aleksandra.horubala@gmail.com)
