<template id="">
  <Layout>

<section>
  <h3>POWSTANIE ŚWIĄTYNI</h3>
    <div class="figure"><img src="../assets/fotosy/model-kaplicy-1.jpg"alt=""></div>
    <p>Pierwszą świątynię (kaplica pw. NMP i św. Barbary i św. Zofii) zbudował w 1396 wójt lubelski Wawrzyniec. Powstała na gruncie ofiarowanym przez wdowę o imieniu Woyczecha. Przy końcu XIV wieku, wdowa przekazała miastu swój majątek (trzy łany pola i dom z zabudowaniami) pod warunkiem wybudowania tu kaplicy. Fundację świątyni zatwierdził i kaplicę poświęcił bp krakowski Piotr Wysz. Posługę duszpasterską pełnił zwykle jeden kapłan, w ówczesnej terminologii zw. prebendarzem.</p>
  </section>
  <section>
    <div class="figure"><img src="../assets/fotosy/model-kaplicy-1-1.jpg"alt=""></div>
    <div class="figure"><img src="../assets/fotosy/model-kaplicy-2.jpg"alt=""></div>
    <div class="figure"><img src="../assets/fotosy/model-kaplicy-3.jpg"alt=""></div>
    <div class="figure"><img src="../assets/fotosy/model-kaplicy-4.jpg"alt=""></div>
  </section>
    <section>
    <p>Była to świątynia złożona z prezbiterium, zakrystii, korpusu nawy i kaplicy. Według Jerzego Siennickiego kaplica mogła istnieć w miejscu później wzniesionej wieży. Zdaniem ks. Wadowskiego mieściła się na terenie kaplicy północnej pw. Najświętszej Maryi Panny.</p>
    <p>Z najnowszych ustaleń wynika, że gotyckie prezbiterium pokrywa się w rzucie z dotąd istniejącym, że było dwuprzęsłowe, od początku zamknięte od wschodu trzema ścianami dziesięcioboku, przykryte sklepieniem krzyżowo-żebrowym, opięte przyporami, doświetlone oknem od wschodu, oraz oknami od południa i jednym od północy. Elewacje prezbiterium i ściany przypór obiegał kamienny gzyms.</p>
    <p>Z prezbiterium powstał aneks północny, pełniący funkcję zakrystii, w które było mieszkaniem Gertrudy Firlej z Opalińskich matki przyszłej ksieni Doroty. Zewnętrzne ściany zakrystii były spięte gzymsem, ale umieszczonym niżej niż na północnej elewacji prezbiterium, a obie budowle obiegał niski cokół jednakowej wysokości. Na początku XV wieku, zniszczeniu albo rozebraniu uległa północna i zachodnia ściana tego korpusu.</p>
  </section>
  <section>
    <p>1396 – Woyczecha wdowa po Dominiku przekazała na cele religijne 3 łany pola z zabudowaniami. Rajcowie lubelscy udali się do Piotra biskupa krakowskiego z prośbą o wyrażenie zgody na budowę kościoła NMP i św. Barbary, św. Zofii i uposażenie prebendarza.</p>
    <p>Sam biskup w otoczeniu prałatów i doktorów krakowskich dopełnił obrzędu założenia kościoła. Pierwszym prebendarzem został ks. Maciej. Rajcy lubelscy uczynili stosowny zapis odnośnie uposażenia w sądzie wójtowskim lubelskim.</p>
    <p>1406 Piotr biskup krakowski i Jakób biskup wileński nadają odpusty temu kościołowi, nazywając go kaplicą św. Zofii i dodając że tę kaplicę zbudował Warzyniec wójt lubelski</p>
    <p>15 lipca 1410 r. zwycięstwo oręża polsko-litewskiego pod wodzą króla Władysława Jagiełły nad Krzyżakami pod Grunwaldem i Tannenbergiem. Król pamiętał, że Bogu zawdzięcza to zwycięstwo, które zakończyło wiekowe krzywdy i powstrzymało drapieżne zapędy Krzyżaków.</p>
    <p>Po zwycięskiej bitwie mistrzowie życia duchownego wyjaśnili królowi, że klęskę Krzyżakom przepowiedziała św. Brygida Szwedzka, dlatego też król postanowił wybudować pomnik wdzięczności Bogu powierzając go opiece zakonowi założonemu przez św. Brygidę.</p>
    <p>Wejście do tej kaplicy możemy oglądać w tzw. „kapsule czasu”, które znajduje się w nawie głównej w pobliżu wejścia do świątyni. Makieta kaplicy z 1396 r. znajduje się w wieży kościoła, obok niej została ustawiona makieta kościoła z czasów współczesnych.</p>
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
      allSections: 4,
      level2: 2,
      level3: 4
    }
  }
}

</script>
<style >
</style>
