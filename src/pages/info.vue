<template id="">
  <Layout>
<section>
  <p>Projekt pn.: Cyfrowa historia Kościoła Pobrygidkowskiego – etap III obejmuje wykonanie multimedialnej instalacji prezentującej niezwykła historię powstania Kościoła Rektoralnego pw.&nbsp;Wniebowzięcia Najświętszej Marii Panny w&nbsp;Lublinie – wotum króla Władysława Jagiełły za&nbsp;zwycięstwo Jagiełły w&nbsp;bitwie pod&nbsp;Grunwaldem, wraz z&nbsp;digitalizacja 141 obiektów, w&nbsp;tym zabytkowych poddanych pracom konserwatorskim po&nbsp;2016 roku.</p>





<p>Specjalnie na&nbsp;potrzeby instalacji, wykorzystano również zdigitalizowane zasoby w&nbsp;ramach działania
  – Kultura Cyfrowa 2016 i&nbsp;2017 zasoby.</p>

<img src="../assets/fotosy/faza5a.webp" alt="dfvfv"  style="max-width: 45vw; margin: 0 0 0 25vw;">


<p>Wszystko zostało ujęte w&nbsp;formie interaktywnej aplikacji, dostępnej na&nbsp;stole multimedialnym i&nbsp;w&nbsp;Internecie.</p>



<p></p>



<p>Instalacja składa się z&nbsp;modułów ułożonych chronologiczne:</p>



<p><strong>1.<a href="http://swbrygida.pl/sw-brygida-i-jej-proroctwo/">Święta Brygida i&nbsp;jej proroctwo</a></strong></p>



<p><strong>2.<a href="http://swbrygida.pl/zwyciestwo-jagielly-w-bitwie-pod-grunwaldem/">Zwycięstwo Jagiełły w&nbsp;bitwie pod&nbsp;Grunwaldem</a></strong></p>



<p><strong>3. Architektura</strong></p>



<p>– <a href="http://swbrygida.pl/architektura/faza-i-kaplica-pw-nmp-sw-barbary-i-sw-zofii-z-1396-r/">faza I&nbsp;– Kaplica pw.&nbsp;NMP, św.&nbsp;Barbary i&nbsp;św.&nbsp;Zofii z&nbsp;1396 r.</a></p>



<p><a href="http://swbrygida.pl/architektura/faza-ii-pomnik-wdziecznosci-krola-wladyslawa-jagielly-za-grunwaldzkie-zwyciestwo/">– faza II – Pomnik wdzięczności króla Władysława Jagiełły za&nbsp;grunwaldzkie zwycięstwo</a></p>



<p>– <a href="http://swbrygida.pl/architektura/faza-iii-przebudowa-swiatyni-ok-1470-1480/">faza III – Przebudowa świątyni ok. 1470 – 1480</a></p>



<p>– <a href="http://swbrygida.pl/architektura/faza-iv-po-1500-r-do-ok-1530/">faza IV – po&nbsp;1500 r. do&nbsp;ok. 1530</a></p>



<p>– <a href="http://swbrygida.pl/architektura/faza-v-wspolczesna-bryla-kosciola/">faza V – współczesna bryła kościoła</a></p>



<p><strong>4. Historia:</strong></p>



<p>– <a href="http://swbrygida.pl/historia/powstanie-i-budowa-kosciola/">powstanie i&nbsp;budowa kościoła</a>,</p>



<p>– <a href="http://swbrygida.pl/historia/pomnik-wdziecznosci-za-zwyciestwo-pod-grunwaldem/">pomnik wdzięczności za&nbsp;zwycięstwo pod&nbsp;Grunwaldem</a></p>



<p>– <a href="http://swbrygida.pl/historia/okres-siostr-brygidek/">okres Sióstr Brygidek</a>,</p>



<p>– <a href="http://swbrygida.pl/historia/okres-siostr-wizytek/">okres Sióstr Wizytek</a>,</p>



<p>– <a href="http://swbrygida.pl/historia/koniec-xix-wieku-i-pierwsza-polowa-xx-wieku/">koniec XIX wieku i&nbsp;pierwsza połowa XX wieku</a></p>



<p>– <a href="http://swbrygida.pl/historia/czasy-wspolczesne-lubelskie-sanktuarium-pamieci-narodowej/">czasy współczesne – Lubelskie Sanktuarium Pamięci Narodowej</a><br></p>



<p>– <a href="http://swbrygida.pl/historia/wielka-renowacja/">wielka renowacja</a>:</p>



<p><a href="http://swbrygida.pl/historia/ekspozycja-historyczna/">ekspozycja historyczna</a></p>



<p><a href="http://swbrygida.pl/historia/ekspozycja-archeologiczna/">ekspozycja archeologiczna</a></p>



<p><a href="http://swbrygida.pl/historia/ekspozycja-numizmatyczna/">ekspozycja numizmatyczna</a></p>



<p><strong>5. Zabytki</strong></p>



<p>– <a href="http://swbrygida.pl/zabytki/okres-siostr-brygidek/">okres Sióstr Brygidek</a>,</p>



<p>– <a href="http://swbrygida.pl/zabytki/okres-siostr-wizytek/">okres Sióstr Wizytek</a>,</p>



<p><strong>6. <a href="http://swbrygida.pl/kalendarium-najwazniejszych-wydarzen/">Kalendarium najważniejszych wydarzeń</a></strong></p>



<p><strong>7. <a href="http://swbrygida.pl/rektorzy-i-kaplani-zwiazani-z-kosciolem-pobrygidkowskim/">Rektorzy i&nbsp;kapłani związani z&nbsp;Kościołem Pobrygidkowskim</a></strong></p>











</section>

</Layout>
</template>
<script>
import { TimelineLite, TweenMax, gsap } from 'gsap';
import Arrows from '~/components/Arrows.vue';

  export default {
    mounted() {
      let numberX = this.clicker;
      let numberP = 'section:nth-child(' + numberX + ')';
      let loader2 = document.querySelector(numberP)
      // timeline.from(loader2, 1.6, {visibility: "visible", x: '-100%', opacity: 0,}).to(loader2, 1, {visibility: "visible", backgroundColor: '#FF0000', color: 'green '});
      gsap.from(loader2, 1.6, {display: "block", y: '100%', opacity: 0,});
      gsap.to(loader2, 1, {delay: 1.6, display: "block", backgroundColor: '#000', color: 'white '});
    },
    data() {
      return {
        poziom:1,
        clicker: 1,
        allSections: 1
      }
    }
  }
</script>
<style>

</style>
