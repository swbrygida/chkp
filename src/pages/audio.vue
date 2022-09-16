
  <template>
    <Layout>
        <!-- <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css" integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/" crossorigin="anonymous"> -->

<div class="playerCalak">


<div class="playerAudio">

  <div class="czasownik">
    <button class="pleyki" v-if="!gra" @click="play2">
      <svg version="1.1" id="Layer_1" x="0px" y="0px" viewBox="0 0 485 485" style="enable-background:new 0 0 485 485;" xml:space="preserve" sodipodi:docname="play1.svg" inkscape:version="1.1.1 (3bf5ae0d25, 2021-09-20)" xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape" xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd" xmlns="http://www.w3.org/2000/svg" xmlns:svg="http://www.w3.org/2000/svg">
         <path class="svgFill" style="fill-opacity:1;stroke:none;stroke-width:1.21824" d="m 181.11908,242.5 v -93.62505 l 34.01652,19.64824 c 18.70909,10.80653 55.03873,31.7892 80.73254,46.62815 25.69381,14.83895 46.71602,27.14585 46.71602,27.34866 0,0.20281 -21.02221,12.50971 -46.71602,27.34866 -25.69381,14.83895 -62.02345,35.82162 -80.73254,46.62815 l -34.01652,19.64824 z" id="path1691" />
         <path class="svgFill" style="fill-opacity:1;stroke:none;stroke-width:1.21824" d="M 231.00998,484.3513 C 134.86706,480.13596 49.497508,417.79273 15.447145,326.93121 8.5831944,308.61514 3.9713893,288.73943 1.3989749,266.38716 c -1.00348655,-8.71952 -1.00348655,-39.0548 0,-47.77432 C 7.137462,168.74988 23.685189,128.6059 54.370712,90.105985 62.008847,80.522724 80.618472,61.907904 90.239173,54.227526 131.63955,21.176854 180.40621,2.7073796 231.61471,0.68413876 295.75637,-1.8500888 354.72162,18.895527 402.45324,60.789882 c 68.39499,60.030738 97.28644,153.828198 74.59736,242.183938 -14.96413,58.27324 -52.24571,109.9299 -103.14582,142.91689 -34.95448,22.65306 -77.76154,36.66356 -116.76079,38.21513 -4.39553,0.17487 -9.76073,0.40306 -11.92267,0.50708 -2.16194,0.10401 -8.55704,-0.0137 -14.21134,-0.26162 z m 37.79613,-30.75444 c 25.62385,-3.31613 46.45213,-9.63882 69.04875,-20.96065 59.03725,-29.58003 101.00367,-84.88625 113.53089,-149.61875 2.97347,-15.36494 3.35466,-19.96895 3.35466,-40.51746 0,-20.95406 -0.38386,-25.37505 -3.63107,-41.81964 C 439.6067,142.42834 403.22595,90.821414 351.95761,60.031377 299.07003,28.268876 234.50752,21.111552 175.67643,40.489051 103.51601,64.256906 49.040422,125.68802 33.928339,200.33578 c -3.179868,15.7073 -3.653281,21.15926 -3.661272,42.16422 -0.008,20.96151 0.372938,25.3576 3.623588,41.81964 12.595156,63.78477 54.766414,119.01169 113.254485,148.31657 26.35103,13.20294 51.59809,19.98828 83.2601,22.37681 7.36055,0.55526 29.46707,-0.25998 38.40087,-1.41616 z" id="path1730" /> </svg>
    </button>
    <button class="pleyki" v-if="gra" @click="pause">
      <svg   version="1.1" id="Layer_1" x="0px" y="0px" viewBox="0 0 485 485" style="enable-background:new 0 0 485 485;" xml:space="preserve" sodipodi:docname="pause1.svg" inkscape:version="1.1.1 (3bf5ae0d25, 2021-09-20)" xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape" xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd" xmlns="http://www.w3.org/2000/svg" xmlns:svg="http://www.w3.org/2000/svg">
      <path class="svgFill" style="stroke-width:1.21824" d="M 231.00998,484.3513 C 134.86706,480.13596 49.497508,417.79273 15.447145,326.93121 8.5831944,308.61514 3.9713893,288.73943 1.3989749,266.38716 c -1.00348655,-8.71952 -1.00348655,-39.0548 0,-47.77432 C 7.137462,168.74988 23.685189,128.6059 54.370712,90.105985 62.008847,80.522724 80.618472,61.907904 90.239173,54.227526 131.63955,21.176854 180.40621,2.7073796 231.61471,0.68413876 295.75637,-1.8500888 354.72162,18.895527 402.45324,60.789882 c 68.39499,60.030738 97.28644,153.828198 74.59736,242.183938 -14.96413,58.27324 -52.24571,109.9299 -103.14582,142.91689 -34.95448,22.65306 -77.76154,36.66356 -116.76079,38.21513 -4.39553,0.17487 -9.76073,0.40306 -11.92267,0.50708 -2.16194,0.10401 -8.55704,-0.0137 -14.21134,-0.26162 z m 37.79613,-30.75444 c 25.62385,-3.31613 46.45213,-9.63882 69.04875,-20.96065 59.03725,-29.58003 101.00367,-84.88625 113.53089,-149.61875 2.97347,-15.36494 3.35466,-19.96895 3.35466,-40.51746 0,-20.95406 -0.38386,-25.37505 -3.63107,-41.81964 C 439.6067,142.42834 403.22595,90.821414 351.95761,60.031377 299.07003,28.268876 234.50752,21.111552 175.67643,40.489051 103.51601,64.256906 49.040422,125.68802 33.928339,200.33578 c -3.179868,15.7073 -3.653281,21.15926 -3.661272,42.16422 -0.008,20.96151 0.372938,25.3576 3.623588,41.81964 12.595156,63.78477 54.766414,119.01169 113.254485,148.31657 26.35103,13.20294 51.59809,19.98828 83.2601,22.37681 7.36055,0.55526 29.46707,-0.25998 38.40087,-1.41616 z"  id="path1972" />
       <path class="svgFill" style="stroke-width:1.21824" d="M 172.65274,242.5 V 140.29925 h 27.21322 27.21322 V 242.5 344.70075 h -27.21322 -27.21322 z"   id="path2011" />
         <path class="svgFill"   style="stroke-width:1.21824"   d="M 257.92082,242.5 V 140.29925 h 27.21322 27.21322 V 242.5 344.70075 h -27.21322 -27.21322 z"   id="path2050" /></svg>

    </button>

  <p class="time">{{ currentTime }}</p>
  <!-- <p class="time">{{ currentTime }}<span>({{numer}} / 74):</span></p> -->


          <button class="pleyki"  @click="nextTrack">
            <svg  version="1.1" id="Capa_1" x="0px" y="0px" viewBox="0 0 235.592 235.592" style="enable-background:new 0 0 235.592 235.592;" xml:space="preserve" sodipodi:docname="next1.svg" inkscape:version="1.1.1 (3bf5ae0d25, 2021-09-20)" xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape" xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd" xmlns="http://www.w3.org/2000/svg" xmlns:svg="http://www.w3.org/2000/svg">
            <path   class="svgFill" style="stroke-width:0.591767"  d="M 112.65527,235.27807 C 91.416442,234.4218 70.715035,227.65936 52.876009,215.75025 23.224368,195.95518 4.414702,164.7819 0.68406083,129.25247 c -0.49943229,-4.75644 -0.49943229,-18.15651 0,-22.91294 C 4.4137767,70.818913 23.30074,39.515546 52.876009,19.836278 69.396501,8.8436077 87.573569,2.4552603 107.65444,0.58434658 c 4.3575,-0.40598288 15.95725,-0.40401172 20.28311,0.003447 19.80583,1.86553792 37.88468,8.12906382 54.04405,18.72388342 24.67223,16.17625 42.50366,41.002664 49.74244,69.255638 2.62419,10.242218 3.55008,17.865255 3.55008,29.228685 0,9.01318 -0.38501,13.61874 -1.76812,21.1504 -5.91685,32.21998 -25.27618,60.76953 -53.14006,78.36659 -16.82452,10.62531 -37.34469,17.16978 -55.96044,17.84738 -2.3427,0.0853 -4.85431,0.19061 -5.58136,0.23408 -0.72704,0.0435 -3.50303,-0.009 -6.16887,-0.11638 z m 15.75169,-15.11692 c 45.29639,-4.75679 82.0664,-38.57208 90.54713,-83.27104 1.26011,-6.64159 1.63129,-10.98623 1.63129,-19.09411 0,-10.27922 -0.80509,-16.81094 -3.20438,-25.997373 -8.70484,-33.329212 -33.62646,-60.199375 -66.17376,-71.347686 -11.10302,-3.80308 -21.28219,-5.469405 -33.41124,-5.469405 -6.94404,0 -12.71115,0.495996 -18.75433,1.612953 -41.675507,7.70286 -74.490616,40.399947 -82.403764,82.107394 -1.267195,6.678947 -1.636481,10.987697 -1.636481,19.094117 0,8.33351 0.377622,12.55192 1.761853,19.68162 3.361953,17.31628 11.238633,33.63563 22.756301,47.14778 2.608996,3.06079 9.197033,9.57929 12.181407,12.05285 16.053694,13.30584 34.703136,21.24277 55.158994,23.47487 5.07935,0.55425 16.30583,0.55843 21.54698,0.008 z" id="path2290" />
            <path class="svgFill" style="stroke-width:0.591767"   d="m 68.296276,171.59004 c -2.237075,-0.7336 -3.726852,-2.05603 -4.674419,-4.14935 -0.594216,-1.3127 -0.598377,-1.65787 -0.598377,-49.64469 0,-47.986822 0.0042,-48.33199 0.598377,-49.6447 0.329107,-0.727045 0.954107,-1.697529 1.388888,-2.156631 1.837647,-1.940443 5.133621,-2.746318 7.514078,-1.837213 0.711694,0.271798 9.734765,6.431729 20.051269,13.688736 l 18.757278,13.194558 0.15258,-10.783775 c 0.16765,-11.849808 0.16338,-11.820788 2.05947,-13.980318 1.50077,-1.709279 3.00798,-2.367193 5.4256,-2.368337 1.44583,-6.84e-4 2.35848,0.161282 3.07419,0.545572 1.56365,0.839572 67.29616,47.124518 68.38505,48.152708 2.8802,2.71964 2.87408,7.66624 -0.0128,10.39126 -1.0809,1.02027 -66.82144,47.30759 -68.37219,48.14024 -0.71572,0.38429 -1.62836,0.54626 -3.0742,0.54557 -2.41762,-0.001 -3.92483,-0.65905 -5.4256,-2.36833 -1.8961,-2.15954 -1.89181,-2.13046 -2.05947,-13.98079 l -0.15259,-10.78425 -18.359721,12.93213 c -10.097849,7.11267 -18.878916,13.203 -19.513482,13.53407 -1.255207,0.65488 -3.989715,0.95859 -5.163891,0.57354 z m 32.709954,-37.63748 c 12.52911,-8.80533 22.78149,-16.07578 22.78308,-16.15656 0.003,-0.15239 -45.362425,-32.09107 -45.827726,-32.26416 -0.154131,-0.05734 -0.263226,13.314709 -0.263226,32.26416 0,19.00549 0.108893,32.32166 0.263842,32.26415 0.145113,-0.0538 10.514928,-7.30227 23.04403,-16.10759 z m 47.69875,0.70223 c 12.08187,-8.49988 22.39983,-15.77948 22.9288,-16.1769 l 0.96177,-0.72257 -22.932,-16.13622 c -12.61261,-8.874921 -22.9927,-16.136219 -23.06689,-16.136219 -0.0742,0 -0.12847,3.668273 -0.12064,8.151718 l 0.0142,8.151721 6.76893,4.70009 c 7.95535,5.5239 9.09591,6.46774 9.95144,8.23501 0.76311,1.57638 0.85798,4.19723 0.20823,5.75231 -0.76848,1.83921 -2.07598,2.9586 -9.56783,8.19123 l -7.36027,5.14072 -0.0145,8.15172 c -0.008,4.48344 0.0476,8.15171 0.1236,8.15171 0.0759,0 10.02324,-6.95444 22.1051,-15.45432 z"  id="path2329" /></svg>

          </button>

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
              <span class="ktoryZ">({{numer}} / 74):</span>
              <h2 >{{ title }} </h2>
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
        currentTime: '0 : 00',
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
          {nr: 74, tytul: 'Księża związani z Kościołem', src: 'music/7.15.Rektorzy kościoła księża związani z Kościołem.mp3', img: 'music/a3.png'}



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
        this.numer = this.numer + 1 ;




      },
      play(numer) {

        this.$refs.audioPlayer.pause();
        this.gra = false;
        this.numer = numer;
        this.src = this.lista[numer].src;
        this.title = this.lista[numer].tytul;
        setTimeout(function() {
          const audio = document.getElementById('audio');
          audio.play();
        }, 100);
        this.gra = true;



      },
      play2() {
        this.$refs.audioPlayer.play();
        this.gra = true;



      },
      pause() {
        this.$refs.audioPlayer.pause();
        this.gra = false;
      },
      onPlaying() {
        // const { audioPlayer } = this.$refs;
        // if (!audioPlayer) {
        //   return;
        // }
        const audio = document.getElementById('audio');
        let secondsNow = Math.round(audio.currentTime % 59);
        let minutesNow = Math.floor(audio.currentTime / 59);
        let secondsNowShow;
        if (secondsNow < 10) {
          secondsNowShow = "0" + secondsNow;
        } else {
          secondsNowShow = secondsNow;
        };
        this.currentTime = minutesNow + ' : ' + secondsNowShow ;
        this.seekValue = (audio.currentTime / audio.duration) * 100;
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
.time span {
    font-size: small;
    line-height: 1em;
  }
  .ktoryZ {
    font-size: small;
  }
  .sciezka {
    width: 100%;
  }

  .pleyki:hover {
          box-shadow: 0 5px 5px #ffee10;
          text-shadow: 0 0 5px #ffee10;
  }
.czasownik p {
  width: 6em;
  text-align: center;
  height: auto;
  display: flex;
  flex-direction: column;
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
  color: #ffee10;
  box-shadow: 0 0 5px #ffee10;
  text-shadow: 0 0 5px #ffee10;
}
svg {
  fill: #666666;
}
.pleyki:hover > svg > .svgFill{
  fill: #ffee10;
}

input[type="range"] {
  -webkit-appearance: none;
  height: 3px;
  background: rgba(255, 255, 255, 0.6);
  border-radius: 5px;
  background-color: #ffee10;
}
input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  height: 20px;
  width: 20px;
  border-radius: 50%;
  background: #ffee10;
  cursor: ew-resize;
  box-shadow: 0 0 2px 0 #555;
}

input[type="range"]::-moz-range-thumb {
  -webkit-appearance: none;
  height: 20px;
  width: 20px;
  border-radius: 50%;
  background: #ffee10;
  cursor: ew-resize;
  box-shadow: 0 0 2px 0 #555;
}

input[type="range"]::-ms-thumb {
  -webkit-appearance: none;
  height: 20px;
  width: 20px;
  border-radius: 50%;
  background: #ffee10;
  cursor: ew-resize;
  box-shadow: 0 0 2px 0 #555;
}





@media screen and (orientation:landscape) {
  .pleyki {
    background-color: transparent;
    width: 10%;
    height: auto;
    border: none;
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
