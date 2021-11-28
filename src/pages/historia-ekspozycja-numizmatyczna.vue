<template id="">
  <Layout>
<section>


  <p>Na pierwszym poziomie wieży znajdują się gabloty zawierającą monety pozyskane w czasie prac archeologicznych. Większość z nich została znaleziona pod posadzką świątyni.</p>
  <div class="figure"><img src="../assets/fotosy/Ekspozycja-numizmatyczna-2.jpg" alt=""></div>
</section>
  <section>
  <p>Numizmaty zaprezentowano w porządku chronologicznym. Powyżej, każdej z monet znajduje się powiększone zdjęcie jej awersu i rewersu.</p>
  <p><strong>W pierwszej szufladzie</strong> umieszczone są numizmaty bite przez Jagiellonów w średniowieczu. Kolekcję tę tworzą głównie denary koronne poszczególnych monarchów.</p>
  <p>Słowo „denar” pochodzi z łaciny – denarius, były one bite w cesarstwie rzymskim od początku III w. n.e., a w całej wczesnośredniowiecznej Europie mianem „denar” określano niemal każdą srebrną monetę. W XIV i XV była najmniejszą jednostką krążącą w obiegu. Za 1 denara można było kupić np. porcję sera.</p>
  <p>Większy nominał stanowił 1 grosz, za który można było nabyć kurę, ale za kapłona należało już zapłacić 2 grosze, zaś za konia – 500 groszy. W czasach Jagiełły pasterz na Śląsku w ciągu całego roku zarabiał 12 groszy, czyli tyle ile była warta 1 para butów.</p>
  <p>Grosze dzieliły się na półgrosze, szelągi (1/3 grosza) oraz kwartalniki – grosza. Relacja grosza do denara stale się zmieniała na niekorzyść tego drugiego – na 1 grosz, w czasach Jagiełły, wchodziło 12 denarów, a pod koniec XV w. – już 16.</p>
</section>
  <section>
  <p><strong>W drugiej szufladzie</strong> znajdują się monety polskich monarchów z okresu nowożytnego – od XVI wieku do III rozbioru Polski, w 1795 r. Kolekcję tę otwierają numizmaty Zygmunta I Starego, syna Jana Kazimierza i wnuka Władysława Jagiełły. W tym okresie denary wychodziły z użycia, choć nadal były w obiegu. Bito je w różnych mennicach i były środkiem płatniczym na wybranym obszarze. Z tego względu mają różne epitety – „elbląski”, „pruski”, „koronny”, „litewski”. Najpopularniejszą monetą stał się grosz oraz jego wielokrotności – jak np. „półtorak” Zygmunta III Wazy, warty 1,5 grosza. Doszło do tego, że za rządów Jana Kazimierza żołd wypłacany był w workach wypełnionych szelągami, takimi jakie znajdują się na ekspozycji. Była to największa w dziejach Pierwszej Rzeczpospolitej inflacja.</p>
  <div class="figure"><img src="../assets/fotosy/Ekspozycja-numizmatyczna.jpg" alt=""></div>
</section>
  <section>
  <p><strong>W trzeciej szufladzie</strong> umieszczono znaki mennicze obcych władców, których panowanie w rodzimych krajach w różny sposób było powiązane z losami Polski w okresie nowożytnym. <strong>Ferdynand I Habsburg</strong> był mężem Anny Jagiellonki – córki króla Czech i Węgier Władysława II Jagiellończyka, a więc dla Władysława Jagiełły był prawnukiem.</p>
  <div class="figure"><img src="../assets/fotosy/Ekspozycja-numizmatyczna-3.jpg" alt=""></div>
</section>
  <section>
  <p><strong>Albreht Hohenzollern</strong> był także potomkiem Władysława Jagiełły – jego matką była Zofia Jagiellonka, siostra Zygmunta Starego. Wsławił się jako ostatni wielki mistrz zakonu krzyżackiego, który przekształcił go w państwo świeckie – Prusy Książęce. Już, jako jego władca złożył, 10 kwietnia 1525 r. w Krakowie, hołd lenny Zygmuntowi Staremu, czego odbiciem są prezentowane monety.</p>
  <p><strong>Gustaw II Adolf,</strong> pochodził z rodu Wazów, stworzył on podstawy rozkwitu potęgi Szwecji poprzez wewnętrzne reformy, ale także przez aneksję kolejnych ziem na wybrzeżach Bałtyku. W 1621 roku zajął Inflanty wraz z Rygą i rozpoczął bicie własnych szelągów ryskich. W kolejnych latach rozciągnął swą władzę na Kurlandię i część Litwy.</p>
  <p><strong>Krystyna Waza,</strong> królowa Szwecji, ostatnia z rodu Wazów, córka Gustawa II Adolfa, przejęła włości ojca. Ponad to tytułowała się już księżną szczecińską, pomorską i kaszubską. Po abdykacja Jana Kazimierza zamierzała nawet starać się o polską koronę.</p>
  <p><strong>Jerzy Wilhelm Hohenzollern</strong> sprawował na tyle nieudolne rządy nad Prusami Książęcymi, że w 1635 r. Polska przejęła kontrolę nad księstwem.</p>
</section>





<Arrows
:clicker="clicker"
:allSections="allSections"
:level2="level2"
:level3="level3"
   />
</Layout>
</template>

<script>
import { TimelineLite, TweenMax, gsap } from 'gsap';
import Arrows from '~/components/Arrows.vue';


export default {
components: {
Arrows
},
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
      allSections: 5,
      level2: 6,
      level3: 6
    }
  }
}

</script>
<style scoped>
</style>
