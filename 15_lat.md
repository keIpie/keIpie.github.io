---
layout: draw
title:
permalink: /15_lat/
---

<div style="text-align:left; display: flex; align-items: center;">
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="prevImage();" style="border: 0px; background-color:white;"> 
    <span class="arrowhtml">&#8249;</span> </button> 
  </div>
  <div id="div-img" style="flex: 0 0 70%;">
    <img class="vertical-center" id="image" src="{{ site.baseurl }}/images/15_lat/just_watch.png" alt="ide" style="width: 80vw">
    <p style="text-align:center" id="year-sub"> 27.12.2014/27.12.2023 - Don’t believe it, just watch! </p>
  </div>
  <div id="div-txt" style="flex: 0 0 0%; align-items: center;">
    <p style="text-align:left; margin-left: 100px;" id="subtitle"> </p>
  </div>
  <div style="flex: 0 0 10%;" class="vertical-center"><button onclick="nextImage();" style="border: 0px; background-color:white;"> 
    <span class="arrowhtml">&#8250;</span> </button>
  </div>
</div>


<script>

var index      = 0;
var index_no   = 54;
let array      = [0, 8, 16, 25, 32, 41, 49];
var image_list = [
                  "{{ site.baseurl }}/images/15_lat/just_watch.png",
                  "{{ site.baseurl }}/images/15_lat/2014/deskurow.jpg",
                  "{{ site.baseurl }}/images/15_lat/2014/wymyslilam.JPG",
                  "{{ site.baseurl }}/images/15_lat/2014/blue_jeans.png",
                  "{{ site.baseurl }}/images/15_lat/2014/rozpierdolilas.JPG",
                  "{{ site.baseurl }}/images/15_lat/2014/misty.JPG",
                  "{{ site.baseurl }}/images/15_lat/2014/wilczyslad.JPG",
                  "{{ site.baseurl }}/images/15_lat/2014/aleakoncert.jpg",

                  "{{ site.baseurl }}/images/15_lat/2015/znow.jpg",
                  "{{ site.baseurl }}/images/15_lat/2015/piano.jpg",
                  "{{ site.baseurl }}/images/15_lat/2015/onaczarna.png",
                  "{{ site.baseurl }}/images/15_lat/2015/jaskolka.JPG",
                  "{{ site.baseurl }}/images/15_lat/2015/calusy.jpg",
                  "{{ site.baseurl }}/images/15_lat/2015/remont.jpg",
                  "{{ site.baseurl }}/images/15_lat/2015/mnm-luzna.jpg",
                  "{{ site.baseurl }}/images/15_lat/2015/mimuw.png",
                  
                  "{{ site.baseurl }}/images/15_lat/2016/przepasc.png",
                  "{{ site.baseurl }}/images/15_lat/2016/bistro.png",
                  "{{ site.baseurl }}/images/15_lat/2016/czarna_hancza.JPG",
                  "{{ site.baseurl }}/images/15_lat/2016/iskra.png",
                  "{{ site.baseurl }}/images/15_lat/2016/srebrzy.png",
                  "{{ site.baseurl }}/images/15_lat/2016/falling.png",
                  "{{ site.baseurl }}/images/15_lat/2016/okosmoka.png",
                  "{{ site.baseurl }}/images/15_lat/2016/czolg.JPG",
                  "{{ site.baseurl }}/images/15_lat/2016/jungle.png",

                  "{{ site.baseurl }}/images/15_lat/2017/tancz.png",
                  "{{ site.baseurl }}/images/15_lat/2017/bojery.png",
                  "{{ site.baseurl }}/images/15_lat/2017/zegarmistrz.png",
                  "{{ site.baseurl }}/images/15_lat/2017/bernardynska.png",
                  "{{ site.baseurl }}/images/15_lat/2017/slub.png",
                  "{{ site.baseurl }}/images/15_lat/2017/portugalia.jpg",
                  "{{ site.baseurl }}/images/15_lat/2017/gotham.png",

                  "{{ site.baseurl }}/images/15_lat/2018/volvo.png",
                  "{{ site.baseurl }}/images/15_lat/2018/lapared.png",
                  "{{ site.baseurl }}/images/15_lat/2018/fuerta.png",
                  "{{ site.baseurl }}/images/15_lat/2018/prysznic.png",
                  "{{ site.baseurl }}/images/15_lat/2018/szpital.jpg",
                  "{{ site.baseurl }}/images/15_lat/2018/rebel.jpg",
                  "{{ site.baseurl }}/images/15_lat/2018/dom-wrobli.png",
                  "{{ site.baseurl }}/images/15_lat/2018/grancanaria.png",
                  "{{ site.baseurl }}/images/15_lat/2018/piorun.png",

                  "{{ site.baseurl }}/images/15_lat/2019/jeruszalaim.jpg",
                  "{{ site.baseurl }}/images/15_lat/2019/garda.jpg",
                  "{{ site.baseurl }}/images/15_lat/2019/lusterko.jpg",
                  "{{ site.baseurl }}/images/15_lat/2019/siniak.jpg",
                  "{{ site.baseurl }}/images/15_lat/2019/zmywcia.jpg",
                  "{{ site.baseurl }}/images/15_lat/2019/izrael.JPG",
                  "{{ site.baseurl }}/images/15_lat/2019/call.jpg",
                  "{{ site.baseurl }}/images/15_lat/2019/palma.jpg",

                  "{{ site.baseurl }}/images/15_lat/2023/overthrown.jpg",
                  "{{ site.baseurl }}/images/15_lat/2023/overthrown.jpg",
                  "{{ site.baseurl }}/images/15_lat/2023/czarny_pocisk.jpg",
                  "{{ site.baseurl }}/images/15_lat/2023/oddech.jpg",
                  "{{ site.baseurl }}/images/15_lat/2023/justken.jpg",
                  ]

var text_list = [ "27.12.2014/27.12.2023 - Don’t believe it, just watch!",
                  
                  "Na szarość naszych nocy \n na naszą bezimienność \n na szarość i nijakość \n jutrzejszych naszych marzeń \n na twarzy przezroczystość \n na twarze bez wyrazu \n na nasze oddalenie \n na naszą nieobecność \n i rozmów obojętność \n listek iskierkę cieni \n jak kotwicę \n wbij w nasze serce \n\n Deskurów, maj 2014",
                  "Dzisiaj nagle wymyśliłem Ciebie \n Twoje imię zadźwięczało we mnie \n Choć tyle innych jest \n Znam tylko jego dźwięk \n\n Błota Karwieńskie, sierpień 2014",
                  "Blue jeans, white shirt \n Walked into the room \n you know you made my eyes burn \n It was like James Dean, for sure \n You so fresh to death and sick as ca-cancer \n You were sorta punk rock, I grew up on hip hop \n But you fit me better than my favorite sweater, and I know \n That love is mean, and love hurts \n But I still remember that day we met in December, oh baby \n\n Ursynów 2014", 
                  "Rozpierdoliłaś mi wakacje \n Na dworcu stoję sam \n\n Warszawa-Bieszczady, wrzesień 2014",
                  "Far Over the Misty Mountains Cold \n To Dungeons Deep and Caverns Old \n We must away ere break of day \n To find our long-forgotten gold \n\n The Pines were Roaring on The Heights \n The Winds were Moaning in the Night \n The Fire was Red, it Flaming Spread \n The Trees Like Torches Blazed with Light \n\n Bieszczady, wrzesień 2014",
                  "Za wilczym śladem podążę w zamieć \n I twoje serce wytropię uparte \n Przez gniew i smutek, stwardniałe w kamień \n Rozpalę usta     smagane wiatrem \n\n Bieszczady, wrzesień 2014",
                  "A śnieg biały błyska pod czarnymi kołami \n Tu czas odmierzamy pustymi flaszkami \n Dla ludzi umarłych już nie ma zbawienia \n Pod stalowym niebem nic się nie zmienia \n\n 2 koła, listopad 2014",
                  
                  "Znów wędrujemy ciepłym krajem, malachitową łąką morza - 2015",
                  "And the newspapers were fooling \n And the ash-trays have retired \n Cause the piano has been drinking \n The piano has been drinking \n The piano has been drinking, not me \n Not me, not me, not me, not me \n\n Londyn, luty 2015",
                  "Nie nasza rzecz nasza rzecz naszą robić rzecz \n\n Verfluchten polnischen, polnischen \n partisanen, banditen, banditen \n\n Halo halo! \n Tutaj Londyn! tutaj Londyn! \n Ona czarna, \n A on blondyn, a on blodyn \n\n Londyn, luty 2015",
                  "Jaskółka czarny sztylet, wydarty z piersi wiatru \n Nagła smutku kotwica, z niewidzialnego jachtu \n Katedra ją złowiła w sklepienia sieć wysoką \n Jak śmierć kamienna bryła \n Jak wyrok naw prostokąt \n Jaskółka błyskawica w kościele obumarłym \n Tnie jak czarne nożyce lęk, który ją ogarnia \n\n Londyn, luty 2015",
                  "Hey, brother, nice and steady \n Put down your drink, you ready \n It's hard when things get messy \n (They call it lonely digging) \n Your booty shaking, you know \n Your head has no right to say no \n Tonight it's ready, set, go \n Baby can you move it round the rhythm \n So we can get with'em \n To the ground and get us a rock and roll round \n Just a downtown body body coming with a super-hottie \n Let's go, yes, no, hell no \n\n Warszawa-Berlin Express, 26.05.2015",
                  "Must be the reason \n why I'm king of my castle \n Must be the reason \n why I'm freeing my trapped soul \n Must be the reason \n why I'm king of my castle \n Must be a reason \n why I'm making examples of you \n\n Neseberska, lipiec 2015",
                  "Czy to gawron był takim mistrzem w swoim rzemiośle, czy to samochód był tak doskonały, dość że wkrótce otworzywszy oczy zobaczyła pod sobą nie ciemność boru, lecz rozedrgane jezioro świateł Moskwy. \n\n Warszawa, sierpień 2015",
                  "Automaty liczą, liczą, liczą \n Liczą cały czas \n Automaty liczą na człowieka \n Automaty liczą, programują, odgarniają śnieg \n Liczną liczbą liczą obliczenia, \n Automaty, liczą, mylą się, a powinny nie \n Automaty automatyzują \n Automaty szybko niszczą się \n Ale znowu się reprodukują \n (...) \n Wielkie automaty liczą nas, segregują nas, \n Małych ludzi, co je obsługują, \n Wykonują rzędy długich liczb, \n Niewiadomych liczb, \n Oznaczają nas symbolem x \n\n MIMUW, wrzesień 2015",

                  "Możesz słuchać plusku wody, możesz zostać z nią do rana - 2016",
                  "Nie pasuję do tego miejsca \n Tutaj siedzi liga pierwsza \n I choć miłość najważniejsza \n Nie zbliża mnie do zwycięstwa \n\n Sopot, 26.05.2016",
                  "Reggae reggae reggae bieszczadzkie \n Reggae reggae reggae \n Słońcem pachnące ma jagód smak \n Reggae reggae reggae bieszczadzkie \n Reggae reggae reggae \n Jak potok rwące przed siebie gna \n\n Czarna Hańcza, lipiec 2016",
                  "Bądź, bądź, bądź dla mnie iskrą \n A kiedy z nieba spłynie jakaś szarość \n Rozpalę naszą rzeczywistość \n Bądź, bądź, bądź Panią świata \n A kiedy spojrzę znowu na Twoją twarz \n Przypomnę sobie smak lata \n\n Czarna Hańcza, lipiec 2016",
                  "Dziewczyny szare, płaskie jak filc \n Słuchają pustych słów \n Poprzez tysiące mroźnych mil \n Srebrzy im piersi nów \n A jak majowy dzwon na dnie \n Gdy zatopiony w drzwi \n Tak w piersiach serca tłuką się \n Serca koloru krwi \n\n Rodonit, sierpień 2016",
                  "Well I turn around to look at you \n You light a cigarette \n The guy you're with he's up and split \n The chair next to you's free \n And I hope that you don't fall in love with me \n\n Albania, sierpień 2016",
                  "Patrzę w oko smoka \n i wzruszam ramionami. \n Jest czerwiec. Wyraźnie. \n Tuż po południu była burza. \n Zmierzch zapada najpierw \n na idealnie kwadratowych skwerach. \n\n Albania, sierpień 2016",
                  "Wszyscy z drogi idę jak czołg \n To miasto będzie dziś zdobyte \n Poddajcie się! Poddajcie się! Dziewczyny też \n Kto nie jest ze mną na przeciwko jest \n Tu będzie bal, tu będzie bal, czy chcesz czy nie \n\n Tirana, sierpień 2016",
                  "Welcome to the jungle \n We’ve got fun and games \n We’ve got everything you want \n Hon we know the names! \n\n Czarnogóra, sierpień 2016",
                  
                  "To nie karnawał, ale tańczyć chcę i będę tańczył z nią co dzień - 2017",
                  "I’m on a boat! \n I’m on a boat! \n Everybody look at me \n cause I’m sailing on a boat! \n\n Giżycko, styczeń 2017",
                  "A kiedy przyjdzie także po mnie \n Zegarmistrz światła purpurowy \n By mi zabełtać błękit w głowie \n To będę jasny i gotowy \n\n Lwów, maj 2017",
                  "Z jakiegoś okna leci fu-gee-la-la \n widać że płynie ostatni letni balet \n zniknięty wieczór zniknięte słowa \n zniknięty facet \n\n Idę przez osiedle jak przez tren \n Ostatni Dzień Sierpnia roztapia się \n W windzie pachnie mokrym psem \n patrzę w lustro w którym nie odbijam się \n jest mnie za mało na lustra \n\n Czerniaków, Bernardyńska Woda, czerwiec 2017",
                  "Kiedy przypłynie perłowa łódź \n Jak o tym śpiewa serce \n Ja Cię zawołam na cały głos \n Nie nie opuszczaj mnie już więcej \n\n Służew, 17.09.2017",
                  "Zaopiekuj się mną \n Nawet, gdy powodów brak! \n Zaopiekuj się mną, \n Mocno tak! \n\n I prawie kochasz mnie \n I jesteś obok! \n Już nienawidzę Cię, \n Tak kolorową! \n\n Portugalia, lipiec 2017",
                  "Ja opuszczam Gotham z Kobietą Kotem! \n\n mój pojazd rdzewieje na parkingu \n mój kostium mam w walizce, nie użyję go nigdy \n\n tak bardzo chciałem żeby przetrwało \n a teraz już mi się nie chce \n i niech to miasto sczeźnie \n'n Warszawa, sierpień 2017",
                  
                  "Ohhh, I can't quit you, baby, So I'm gonna put you down for awhile! - 2018",
                  "Omen piekieł kierował \n Twoim statkiem na ten brzeg \n Ojciec mówił mi córko \n Upij w sztok, a poznasz go \n Słowo rzekł się \n Będziesz dzieci mieć \n Czy pamiętasz z kim i gdzie? \n\n La Pared, styczeń 2018",
                  "Tell your heart that I'm the one \n Tell your heart it's me \n I want you \n Rockin' back inside my heart \n I want you \n Rockin' back inside my heart \n Rockin' back inside my heart \n Shadow in my house \n The man he has brown eyes \n She'll never go to Hollywood \n Love moves me \n'n Fuerta, styczeń 2018",
                  "Wybacz proszę, \n Gdy się tak uśmiecham \ n Wybacz proszę \n Lecz nie na to czekam \n\n Wszystko czego dzis chce, \n Pamietaj o tym \n Polecieć chcę \n Tam i z powrotem \n Z ramion twych wprost \n Do nieba, do nieba \n\n Nowy York, kwiecień 2018",
                  "\n\n Szpital Św. Zofii, czerwiec 2018",
                  "You told me once I have a rebel heart \n I don't know if that's true \n But I believe you saw something in me that lives inside you too \n Now all I hear is the wind \n There's a storm coming through \n Did I misplace or forsake my love \n Now that I gave it to you? \n\n Stróża, sierpien 2018",
                  "Nic nie mam \n Zdmuchnęła mnie ta jesień całkiem \n Nawet nie wiem \n Jak tam sprawy za lasem \n Rano wstaję, poemat chwalę \n Biorę się za słowo jak za chleb \n\n Rzeczywiście tak jak księżyc \n Ludzie znają mnie tylko z jednej \n Jesiennej strony \n\n Dziekanów Polski, wrzesień 2018",
                  "Oto święty szczyt \n Jestem tutaj z nim \n Patrzę stąd na Babiloon \n Patrzę stąd na Babiloon \n Hej panie zły, jak się pan ma? \nJak tam pana gra? \n Nie nie nie nie nie nie nie nie tak \n\n Gran Canaria, grudzień 2018",
                  "Ta, nowa rana, ten sam szpital \n Doktor, nic nie pytaj, tylko zszyj tu i zszyj tam \n Ty, chwilka, pęka stów kilka \n Jesteś w moich winklach, to mój squat, park  i drink bar \n Miasto żyje we mnie, we mnie zdycha \n Grzechem stracić jest spryt, nie te brednie, że pycha \n\n Las Palmas, grudzień 2018",

                  "Jerusalem! - 2019",
                  "\n\n Jezioro Garda, maj 2019",
                  "\n\n Włochy, maj 2019",
                  "\n\n Warszawa, czerwiec 2019",
                  "\n\n Warszawa, lipiec 2019",
                  "\n\n Jezioro Genezaret, wrzesień 2019",
                  "\n\n Warszawa / Las Palmas, listopad 2019",
                  "\n\n Legionowo, listopad 2019",

                  "2023",
                  "Your faith was strong but you needed proof \n You saw her bathing on the roof \n Her beauty in the moonlight overthrew you \n She tied you to a kitchen chair \n She broke your throne, and she cut your hair \n And from your lips she drew the Hallelujah \n\n Sycylia, wrzesień 2023",
                  "Mówią na niego Czarny Pocisk \n On samochodem mknie \n W czyste białe światło \n Nucąc rzewną pieśń \n Nie wołaj nie zaklinaj \n Nie usłyszy nic \n Tu nie miał nigdy domu i każdy z niego drwi \n\n Sycylia, wrzesień 2023",
                  "Jeszcze mi głupio \n Jeszcze wstyd \n Nie jestem gotowa \n Nie przyjdą te słowa \n Znasz mnie \n Chyba gdzieś głębiej muszę zejść \n Cała się trzęsę jest mi źle \n Bałagan mam w głowie \n Nie myślę rozsądnie \n\n Warszawa, lipiec 2023",
                  "I'm just Ken (and I'm enough) \n And I'm great at doing stuff \n So, hey, check me out, yeah, I'm just Ken \n My name's Ken (and so am I) \n Put that manly hand in mine \n So, hey, world, check me out, yeah, I'm just Ken \n\n Mazury, lipiec 2023",
                  ]

function formatTextWithLineBreaks(text) {
    return text.replace(/\n/g, "<br>");
}

function prevImage()
{
  var divimg  = document.getElementById("div-img");
  var divtxt  = document.getElementById("div-txt");
  var img     = document.getElementById("image");
  var txt     = document.getElementById("subtitle");
  var yeartxt = document.getElementById("year-sub");

  if (index != 1) {
    index             = (index - 1) % index_no;
    divimg.style.flex = "0 0 50%";
    divtxt.style.flex = "0 0 30%";
    img.src           = image_list[index];
    txt.innerHTML     = formatTextWithLineBreaks(text_list[index]);
    yeartxt.innerHTML = "";
  }
  else {
    index             = (index - 1) % index_no;
    divimg.style.flex = "0 0 70%";
    divtxt.style.flex = "0 0 0%";
    img.src           = image_list[index];
    txt.innerHTML     = "";
    yeartxt.innerHTML = text_list[index];
  }
  return false;
}

function nextImage()
{
  var divimg  = document.getElementById("div-img");
  var divtxt  = document.getElementById("div-txt");
  var img     = document.getElementById("image");
  var txt     = document.getElementById("subtitle");
  var yeartxt = document.getElementById("year-sub");

  if (index != (index_no-1)) {
    index             = (index + 1) % index_no;
    divimg.style.flex = "0 0 50%";
    divtxt.style.flex = "0 0 30%";
    img.src           = image_list[index];
    txt.innerHTML     = formatTextWithLineBreaks(text_list[index]);
    yeartxt.innerHTML = "";
  }
  else {
    index             = (index + 1) % index_no;
    divimg.style.flex = "0 0 70%";
    divtxt.style.flex = "0 0 0%";
    img.src           = image_list[index];
    txt.innerHTML     = "";
    yeartxt.innerHTML = text_list[index];
  }
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
