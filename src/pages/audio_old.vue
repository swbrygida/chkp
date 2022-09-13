
  <template>
    <Layout>
        <!-- <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css" integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/" crossorigin="anonymous"> -->

<div class="playerCalak">


<div class="playerAudio">

  <div class="czasownik">
    <button class="pleyki" v-if="!gra" @click="play2"><g-image alt="play" src="~/assets/play1.svg"  /></button>
    <button class="pleyki" v-if="gra" @click="pause"><g-image alt="pause" src="~/assets/pause1.svg"  /></button>

  <p>{{ currentTime }}</p>

          <button class="pleyki"  @click="nextTrack"><g-image alt="nextTrack" src="~/assets/next1.svg"  /></button>

        <audio
          id="audio"
          :src="this.src"
          ref="audioPlayer"
          @timeupdate="onPlaying"
          @ended="nextTrack()"
        >
          Your browser does not support the
          <code>audio</code> element.
        </audio>
        <!-- <p>{{ durationCalak }}</p> -->
        </div>
        <div class="playerGora">



              <input
              class="sciezka"
                type="range"
                min="0"
                max="100"
                step="1"
                v-model="seekValue"
                @change="onSeek"
              />
              <h2 >{{ title }}</h2>
              </div>
        <div>
          <!-- <i class="pleyki fa-solid fa-circle-play" v-if="!gra" @click="play2" ></i>
          <i class="pleyki fa-solid fa-circle-pause" v-if="gra" @click="pause" ></i>
          <i class="pleyki fa-solid fa-circle-right" @click="nextTrack"></i> -->



        </div>
        </div>
        <!-- <p>numer: {{numer}}</p>
        <p>numerNext: {{numerNextPoka}}</p>
        <p>tablica: {{taTablica}}</p> -->

        <ul class="playLista">
          <li v-for="list in lista"  @click='play(list.nr)' >{{list.tytul}}</li>

        </ul>

</div>
        <ArrowsAudio
        :clicker="clicker"
        :allSections="allSections"
        :level2="level2"
        :level3="level3"
           />

    </Layout>
  </template>



  <script>
  import { TimelineLite, TweenMax, gsap } from 'gsap';
  import ArrowsAudio from '~/components/ArrowsAudio.vue';


  export default {
  components: {
  ArrowsAudio
  },

    data() {
      return {
        poziom:1,
        clicker: 1,
        allSections: 1,
        level2: 2,
        level3: 2,
        currentTime: '0:00',
        seekValue: 0,
        durationCalak: '0:00',
        title: 'Proroctwo, przepowiednia św Brygidy',
        gra: false,
        src: 'music/1.1.PROROCTWO, PRZEPOWIEDNIA SW BRYGIDY.mp3',
        numer: 0,
        numerNextPoka: 1,
        taTablica: 0,
        lista: [
          {nr: 0, tytul: 'Proroctwo, przepowiednia św Brygidy', src: 'music/1.1.PROROCTWO, PRZEPOWIEDNIA SW BRYGIDY.mp3', img: 'music/a1.png'},
          {nr: 1, tytul: 'Przepowiednia św. Brygidy', src: 'music/1.2.Przepowiednia św. Brygidy.mp3', img: 'music/a2.png'},
          {nr: 2, tytul: 'Życiorys i przesłanie św. Brygidy', src: 'music/1.3.Życiorys i przesłanie św. Brygidy.mp3', img: 'music/a3.png'},
          {nr: 3, tytul: 'Św. Brygida', src: 'music/1.4.Św. Brygida.mp3', img: 'music/a1.png'},
          {nr: 4, tytul: 'Modlitwa', src: 'music/1.5.Modlitwa.mp3', img: 'music/a2.png'},
          {nr: 5, tytul: 'Podsumowanie', src: 'music/1.6.Podsumowanie.mp3', img: 'music/a3.png'},
          {nr: 6, tytul: 'Król Władysław Jagiełło', src: 'music/2.1.Król Władysław Jagiełło i jego zwycięstwo.mp3', img: 'music/a3.png'},
          {nr: 7, tytul: 'Król Władysław Jagiełło i jego zwycięstwo', src: 'music/2.2.Król Władysław Jagiełło ZAWARTOŚĆ.mp3', img: 'music/a3.png'},
          {nr: 8, tytul: 'Architektura kaplicyi kościoła', src: 'music/3.1.ARCHITEKTURA KAPLICYI KOŚCIOŁA.mp3', img: 'music/a3.png'},
          {nr: 9, tytul: 'Faza I – Kaplica pw. NMP, św. Barbary i św. Zofii', src: 'music/3.2.Faza I – Kaplica pw. NMP, św. Barbary i św. Zofii.mp3', img: 'music/a3.png'},
          {nr: 10, tytul: 'Faza II – Pomnik wdzięczności króla Władysława Jagiełły za grunwaldzkie zwycięstwo', src: 'music/3.3.Faza II – Pomnik wdzięczności króla Władysława Jagiełły za grunwaldzkie zwycięstwo.mp3', img: 'music/a3.png'},
          {nr: 11, tytul: 'Faza III – Przebudowa świątyni', src: 'music/3.4.Faza III – Przebudowa świątyni.mp3', img: 'music/a3.png'},
          {nr: 12, tytul: 'Faza IV – po 1500 r', src: 'music/3.5.Faza IV – po 1500 r.mp3', img: 'music/a3.png'},
          {nr: 13, tytul: 'Faza V – współczesna bryła kościoła', src: 'music/3.6.Faza V – współczesna bryła kościoła.mp3', img: 'music/a3.png'},
          {nr: 14, tytul: 'Podsumowanie', src: 'music/3.7.Podsumowanie.mp3', img: 'music/a3.png'},
          {nr: 15, tytul: 'Pierwsza faza budowy – gotycka', src: 'music/3.8.Pierwsza faza budowy – gotycka.mp3', img: 'music/a3.png'},
          {nr: 16, tytul: 'Druga faza budowy – nowożytna', src: 'music/3.9.Druga faza budowy – nowożytna.mp3', img: 'music/a3.png'},
          {nr: 17, tytul: 'Historia - powstanie świątyni w 1396 r', src: 'music/4.1.POWSTANIE ŚWIĄTYNI W 1396 r.mp3', img: 'music/a3.png'},
          {nr: 18, tytul: 'Pierwsza świątynia', src: 'music/4.2.Pierwsza świątynia.mp3', img: 'music/a3.png'},
          {nr: 19, tytul: 'Pomnik wdzięczności za zwycięstwo pod Grunwaldem', src: 'music/4.3.POMNIK WDZIĘCZNOŚCI ZA ZWYCIĘSTWO POD GRUNWALDEM.mp3', img: 'music/a3.png'},
          {nr: 20, tytul: 'Okres Sióstr Brygidek 1426 - 1870 r.', src: 'music/4.4.OKRES SIÓSTR BRYGIDEK 1426 - 1870 r.mp3', img: 'music/a3.png'},
          {nr: 21, tytul: 'Okres Sióstr Wizytek 1835 - 1882 r', src: 'music/4.5.OKRES SIÓSTR WIZYTEK 1835 - 1882 r.mp3', img: 'music/a3.png'},
          {nr: 22, tytul: 'Koniec XIX wieku I pierwsza połowa XX wieku', src: 'music/4.6.KONIEC XIX WIEKU I PIERWSZA POŁOWA XX WIEKU.mp3', img: 'music/a3.png'},
          {nr: 23, tytul: 'Kościół Pobrygidkowski – Lubelskie Sanktuarium Pamięci Narodowej', src: 'music/4.7.KOŚCIÓŁ POBRYGIDKOWSKI – LUBELSKIE SANKTUARIUM PAMIĘCI NARODOWEJ.mp3', img: 'music/a3.png'},
          {nr: 24, tytul: 'Wielka renowacja', src: 'music/4.8.WIELKA RENOWACJA.mp3', img: 'music/a3.png'},
          {nr: 25, tytul: 'Kaplica Grunwaldzka', src: 'music/4.9.KAPLICA GRUNWALDZKA.mp3', img: 'music/a3.png'},
          {nr: 26, tytul: 'Sanktuarium św. Brygidy', src: 'music/4.10.SANKTUARIUM ŚW. BRYGIDY.mp3', img: 'music/a3.png'},
          {nr: 27, tytul: 'Lubelskie Sanktuarium Pamięci Narodowej', src: 'music/4.11.LUBELSKIE SANKTUARIUM PAMIĘCI NARODOWEJ.mp3', img: 'music/a3.png'},
          {nr: 28, tytul: 'Ekspozycje', src: 'music/4.12.EKSPOZYCJA HISTORYCZNA, ARCHEOLOGICZNA I NUMIZMATYCZNA.mp3', img: 'music/a3.png'},
          {nr: 29, tytul: 'Ekspozycja historyczna', src: 'music/4.13.EKSPOZYCJA HISTORYCZNA.mp3', img: 'music/a3.png'},
          {nr: 30, tytul: 'Ekspozycja archeologiczna', src: 'music/4.14.EKSPOZYCJA ARCHEOLOGICZNA.mp3', img: 'music/a3.png'},
          {nr: 31, tytul: 'Ekspozycja numizmatyczna', src: 'music/4.15.EKSPOZYCJA NUMIZMATYCZNA.mp3', img: 'music/a3.png'},
          {nr: 32, tytul: 'Zabytki okres Sióstr Brygidek', src: 'music/5.1.1.ZABYTKI OKRES SIÓSTR BRYGIDEK.mp3', img: 'music/a3.png'},
          {nr: 33, tytul: 'Wprowadzenie', src: 'music/5.1.2.Wprowadzenie.mp3', img: 'music/a3.png'},
          {nr: 34, tytul: 'Dekoracja malarska', src: 'music/5.1.3.Dekoracja malarska.mp3', img: 'music/a3.png'},
          {nr: 35, tytul: 'Obraz św. Brygidy', src: 'music/5.1.4.Obraz św. Brygidy.mp3', img: 'music/a3.png'},
          {nr: 36, tytul: 'Krucyfiks XV w', src: 'music/5.1.5.Krucyfiks XV w.mp3', img: 'music/a3.png'},
          {nr: 37, tytul: 'Kamienna płyta', src: 'music/5.1.6.KAMIENNA PŁYTA.mp3', img: 'music/a3.png'},
          {nr: 38, tytul: 'XVII wieczna koncepcja wystroju kościoła', src: 'music/5.1.7.XVII wieczna koncepcja wystroju kościoła.mp3', img: 'music/a3.png'},
          {nr: 39, tytul: 'Obrazy w stallach z historią życia św. Brygidy', src: 'music/5.1.8.Obrazy w stallach z historią życia św. Brygidy.mp3', img: 'music/a3.png'},
          {nr: 40, tytul: 'Dwa cykle obrazów emblematycznych', src: 'music/5.1.9.Dwa cykle obrazów emblematycznych.mp3', img: 'music/a3.png'},
          {nr: 41, tytul: 'Cykl pierwszy – obrazy emblematyczne_ Droga duszy do Boga', src: 'music/5.1.10.cykl pierwszy – obrazy emblematyczne_ Droga duszy do Boga.mp3', img: 'music/a3.png'},
          {nr: 42, tytul: 'Cykl drugi – obrazy emblematyczne nawiązujące do Pisma św.', src: 'music/5.1.11.cykl drugi – obrazy emblematyczne nawiązujące do Pisma św.mp3', img: 'music/a3.png'},
          {nr: 43, tytul: 'Sklepienie prezbiterium', src: 'music/5.1.12.Sklepienie prezbiterium.mp3', img: 'music/a3.png'},
          {nr: 44, tytul: 'Obrazy', src: 'music/5.1.13.Obrazy.mp3', img: 'music/a3.png'},
          {nr: 45, tytul: 'Wniebowzięcia NMP', src: 'music/5.1.14.Wniebowzięcia NMP.mp3', img: 'music/a3.png'},
          {nr: 46, tytul: 'Zwiastowanie NMP', src: 'music/5.1.15.Zwiastowanie NMP.mp3', img: 'music/a3.png'},
          {nr: 47, tytul: 'Św. Kazimierz', src: 'music/5.1.16.św. Kazimierz.mp3', img: 'music/a3.png'},
          {nr: 48, tytul: 'Kult św. Brygidy', src: 'music/5.1.17.Kult św. Brygidy.mp3', img: 'music/a3.png'},
          {nr: 49, tytul: 'Zabytki - okres Sióstr Wizytek', src: 'music/5.2.1.ZABYTKI - OKRES SIÓSTR  WIZYTEK.mp3', img: 'music/a3.png'},
          {nr: 50, tytul: 'Wizytki u Brygidek', src: 'music/5.2.2.Wizytki u Brygidek.mp3', img: 'music/a3.png'},
          {nr: 51, tytul: 'Obraz św. Franciszek Salezy', src: 'music/5.2.3.Obraz św. Franciszek Salezy.mp3', img: 'music/a3.png'},
          {nr: 52, tytul: 'Obraz Józef z Dzieciątkiem', src: 'music/5.2.4Obraz Józef z Dzieciątkiem.mp3', img: 'music/a3.png'},
          {nr: 53, tytul: 'Obraz św. Małgorzata Alacoque', src: 'music/5.2.5.Obraz św. Małgorzata Alacoque.mp3', img: 'music/a3.png'},
          {nr: 54, tytul: 'Podsumowanie', src: 'music/5.2.6.Podsumowanie.mp3', img: 'music/a3.png'},
          {nr: 55, tytul: 'Kalendarium', src: 'music/6.1.KALENDARIUM.mp3', img: 'music/a3.png'},
          {nr: 56, tytul: 'XIV – XVw', src: 'music/6.2.XIV – XVw.mp3', img: 'music/a3.png'},
          {nr: 57, tytul: 'XVI w', src: 'music/6.3.XVI w.mp3', img: 'music/a3.png'},
          {nr: 58, tytul: 'XVII – XVIII w', src: 'music/6.4.XVII – XVIII w.mp3', img: 'music/a3.png'},
          {nr: 59, tytul: 'XIX w', src: 'music/6.5.XIX w.mp3', img: 'music/a3.png'},
          {nr: 60, tytul: 'Rektorzy kościoła', src: 'music/7.1.Rektorzy kościoła czołówka.mp3', img: 'music/a3.png'},
          {nr: 61, tytul: 'Rektorzy kościoła ks Władziński', src: 'music/7.2.Rektorzy kościoła ks Władziński.mp3', img: 'music/a3.png'},
          {nr: 62, tytul: 'Rektorzy kościoła ks Gostyński', src: 'music/7.3.Rektorzy kościoła ks Gostyński.mp3', img: 'music/a3.png'},
          {nr: 63, tytul: 'Rektorzy kościoła ks Poddębniak', src: 'music/7.4.Rektorzy kościoła ks Poddębniak.mp3', img: 'music/a3.png'},
          {nr: 64, tytul: 'Rektorzy kościoła ks Thiel', src: 'music/7.5.Rektorzy kościoła ks Thiel.mp3', img: 'music/a3.png'},
          {nr: 65, tytul: 'Rektorzy kościoła ks Galusiński', src: 'music/7.6.Rektorzy kościoła ks Galusiński.mp3', img: 'music/a3.png'},
          {nr: 66, tytul: 'Rektorzy kościoła ks Słowikowski', src: 'music/7.7.Rektorzy kościoła ks Słowikowski.mp3', img: 'music/a3.png'},
          {nr: 67, tytul: 'Rektorzy kościoła ks Chlastwa', src: 'music/7.8.Rektorzy kościoła ks Chlastwa.mp3', img: 'music/a3.png'},
          {nr: 68, tytul: 'Rektorzy kościoła ks Zakrzewski', src: 'music/7.9.Rektorzy kościoła ks Zakrzewski.mp3', img: 'music/a3.png'},
          {nr: 69, tytul: 'Rektorzy kościoła ks Młynarczyk', src: 'music/7.10.Rektorzy kościoła ks Młynarczyk.mp3', img: 'music/a3.png'},
          {nr: 70, tytul: 'Rektorzy kościoła ks Brzozowski', src: 'music/7.11.Rektorzy kościoła ks Brzozowski.mp3', img: 'music/a3.png'},
          {nr: 71, tytul: 'Rektorzy kościoła ks Czerwiński', src: 'music/7.12.Rektorzy kościoła ks Czerwiński.mp3', img: 'music/a3.png'},
          {nr: 72, tytul: 'Rektorzy kościoła ks Przytuła', src: 'music/7.13.Rektorzy kościoła ks Przytuła.mp3', img: 'music/a3.png'},
          {nr: 73, tytul: 'Rektorzy kościoła ks Bondyra', src: 'music/7.14.Rektorzy kościoła ks Bondyra.mp3', img: 'music/a3.png'},
          {nr: 74, tytul: 'Rektorzy kościoła księża związani z Kościołem', src: 'music/7.15.Rektorzy kościoła księża związani z Kościołem.mp3', img: 'music/a3.png'}



        ]
      }
    },
    mounted() {
        const audio = document.getElementById('audio');
                // audio.addEventListener('ended', p2);
                gsap.from('.playerAudio', 1.6, {display: "fixed",  y: '100%', opacity: 0,});
        gsap.from('.playLista', 2.6, {display: "block",  y: '100%', opacity: 0,});



    },
    methods: {
      nextTrack() {

        // alert('next');
        this.$refs.audioPlayer.pause();
        this.gra = false;


        let numerNext = this.numer + 1;
        this.numerNextPoka = numerNext;


        let tablica = this.lista.length;
        this.taTablica = tablica;
        while (numerNext === tablica) {
          alert('koniec listy utworów');
          this.number = 0;
          numberNext = 1;
          this.numerNextPoka = numerNext;
        };

        this.src = this.lista[numerNext].src;
        this.title = this.lista[numerNext].tytul;
        // this.currentTime = '0:00';
        this.seekValue = 0;
        setTimeout(function() {
          const audio = document.getElementById('audio');
          audio.play();
        }, 100);
        this.gra = true;
        let secondsAll = Math.round(audio.duration % 59);
        let secondsAllShow = secondsAll < 10 ? secondsAllShow = "0" + secondsAll : secondsAllShow = secondsAll;
        let minutesAll = Math.floor(audio.duration / 59);
        this.durationCalak = minutesAll + ':' + secondsAllShow;
        this.numer = this.numer + 1 ;




      },
      play(numer) {

        this.$refs.audioPlayer.pause();
        this.gra = false;
        this.numer = numer;
        this.src = this.lista[numer].src;
        this.title = this.lista[numer].tytul;
        // this.currentTime = '0:00';
        // this.seekValue = 0;
        setTimeout(function() {
          const audio = document.getElementById('audio');
          audio.play();
        }, 100);
        this.gra = true;
        let secondsAll = Math.round(audio.duration % 59);
        let secondsAllShow = secondsAll < 10 ? secondsAllShow = "0" + secondsAll : secondsAllShow = secondsAll;
        let minutesAll = Math.floor(audio.duration / 59);
        this.durationCalak = minutesAll + ':' + secondsAllShow;


      },
      play2() {
        this.$refs.audioPlayer.play();
        this.gra = true;
        let secondsAll = Math.round(this.$refs.audioPlayer.duration % 59);
        let secondsAllShow = secondsAll < 10 ? secondsAllShow = "0" + secondsAll : secondsAllShow = secondsAll;
        let minutesAll = Math.floor(this.$refs.audioPlayer.duration / 59);
        this.durationCalak = minutesAll + ':' + secondsAllShow;


      },
      pause() {
        this.$refs.audioPlayer.pause();
        this.gra = false;
      },
      onPlaying() {
        const { audioPlayer } = this.$refs;
        if (!audioPlayer) {
          return;
        }
        let secondsNow = Math.round(audioPlayer.currentTime % 59);
        let secondsNowShow = secondsNow < 10 ? secondsNowShow = "0" + secondsNow : secondsNowShow = secondsNow;
        let minutesNow = Math.floor(audioPlayer.currentTime / 59);

        this.currentTime = minutesNow + ':' + secondsNowShow ;
        this.seekValue = (audioPlayer.currentTime / audioPlayer.duration) * 100;
      },
      onSeek() {
        const { audioPlayer } = this.$refs;
        const seekto = audioPlayer.duration * (this.seekValue / 100);
        audioPlayer.currentTime = seekto;
      },
    },
  };
  </script>
  <style>
  input[type=range]  {
    max-width: 90%;

  }
  .playerGora {
    display: flex;
    flex-direction: column;
    align-items: center;

  }
  .playerAudio {
    background-color: #333;
    color: gray!important;
    position: fixed;
    top: 0; left:0;
    width: 100vw;
    z-index: 4;

  }
  .sciezka {
    color: #ffee10!important;
  }
  h2, h3 {
    color:#fff;
  }
  .sciezka {
    width: 100%;
  }

  .pleyki:hover {
          box-shadow: 0 10px 10px rgba(0, 0, 0, 0.4);
  }
.czasownik p {
  width: 6em;
  text-align: center;
  height: auto;
}
.czasownik {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 5vh 0;
  max-height: 15vh;

}
.playLista{
  margin: 0;
  padding: 50vh 0 10vh 0;
  margin: 0 10%;
  z-index: 3;

}
.playLista li {
  list-style: none;
  margin: .1em 0;
  padding: 0;
  cursor: pointer;
    font-family: 'Inknut Antiqua', serif;
  font-size: .6em;
  text-align: left;

  overflow: hidden;
}
.playLista li:hover {
  box-shadow: 0 10px 10px rgba(255, 255, 255, 0.4);
}



@media screen and (orientation:landscape) {
  .pleyki {
    background-color: transparent;
    width: 10%;
    height: auto;
    border: none;
  }
  .pleyki  svg {
    filter: hue-rotate(40deg) saturate(0.5) brightness(390%) saturate(4);
  }
}

@media screen and (orientation:portrait) {

  .pleyki {
    background-color: transparent;
    width: 20%;
    height: auto;
    border: none;
  }
  h2, h3 {
    font-size: 1em;
    max-width: 90%;
  }
}

  </style>
