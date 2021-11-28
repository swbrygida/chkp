<template>
  <Layout>
    <div class="loaderF">
    </div>
    <div class="loader">
      <div class="brygida_logo" @click="loaderGo">
        <g-image src="~/assets/brygida_logo_fff.svg" />
      </div>
    </div>
    <div class="menusy">





    <div class="menu">
      <div class="promo" style="--overlay-color: red">
        <g-link to="/proroctwo/">
        <div class="image-wrapper ruch" >
          <g-image src="~/assets/fotosy/Brygida2.jpg" width="500"/>
        </div></g-link>
        <h2 class="title" data-cta="i jej proroctwo →">Święta Brygida</h2>
      </div>
      <div class="promo" style="--overlay-color: orange">
        <g-link to="/zwyciestwo/">
        <div class="image-wrapper ruch" >
          <g-image src="~/assets/fotosy/Pomnik-pod-Grunwaldem.jpg" width="500"/>
        </div></g-link>
        <h2 class="title" data-cta="i zwycięstwo w bitwie pod Grunwaldem →">Król Władysław Jagiełło</h2>
      </div>
      <div class="promo" style="--overlay-color: yellowgreen"  @click="pokaVfaz">
        <div class="image-wrapper ruch" >
          <g-image src="~/assets/fotosy/Architektura.jpg" width="500"/>
          </div>
        <h2 class="title" data-cta="V faz przemiany →"> Architektura!</h2>
      </div>
      <div class="promo" style="--overlay-color: darkgreen" @click="historia">
        <div class="image-wrapper ruch" >
          <g-image src="~/assets/fotosy/historia.jpg" width="500"/>
          </div>
        <h2 class="title" data-cta="do poznania →">Historia</h2>
      </div>
      <div class="promo" style="--overlay-color: blue" @click="zabytki">
        <div class="image-wrapper ruch" >
          <g-image src="~/assets/fotosy/Zabytki-okres-siostr-Brygidek.JPG" width="500"/>
          </div>
        <h2 class="title" data-cta="do obejrzenia →">Zabytki</h2>
      </div>
      <div class="promo" style="--overlay-color: indigo">
        <g-link to="/kalendarium/">
        <div class="image-wrapper ruch" >
          <g-image src="~/assets/fotosy/kalendarz.jpg" width="500"/>
          </div></g-link>
        <h2 class="title" data-cta="najważniejszych wydarzeń →">Kalendarium</h2>
      </div>
      <div class="promo" style="--overlay-color: green">
        <g-link to="/rektorzy/">
        <div class="image-wrapper ruch" >
          <g-image src="~/assets/fotosy/ks. Bondyra Dariusz.JPG" width="500"/>
          </div></g-link>
        <h2 class="title" data-cta="oraz kapłani związani z kościołem →">Rektorzy</h2>
      </div>
      <div class="promo" style="--overlay-color: yellowgreen">
        <g-link to="/info/">
        <div class="image-wrapper ruch" >
          <g-image src="~/assets/fotosy/info.png" width="500"/>
          </div></g-link>
        <h2 class="title" data-cta="o projekcie →">Informacje</h2>
      </div>
        </div><!-- koniec menu  -->

        <div class="submenu" >
          <div class="menu2"  v-show="submenu === 'Vfaz'">
          <div class="promo" style="--overlay-color: red">
            <g-link to="/architektura-faza-1/">
            <div class="image-wrapper ruch" >
              <g-image src="~/assets/fotosy/f1.jpg" width="500"/>
            </div></g-link>
            <h2 class="title" data-cta=" →">I Faza</h2>
          </div>
          <div class="promo" style="--overlay-color: orange">
            <g-link to="/architektura-faza-2/">
            <div class="image-wrapper ruch" >
              <g-image src="~/assets/fotosy/f2.jpg" width="500"/>
            </div></g-link>
            <h2 class="title" data-cta=" →">II Faza</h2>
          </div>
          <div class="promo" style="--overlay-color: yellowgreen">
            <g-link to="/architektura-faza-3/">
            <div class="image-wrapper ruch">
              <g-image src="~/assets/fotosy/f3.jpg" width="500"/>
              </div></g-link>
            <h2 class="title" data-cta=" →"> III Faza</h2>
          </div>
          <div class="promo" style="--overlay-color: darkgreen">
            <g-link to="/architektura-faza-4/">
            <div class="image-wrapper ruch" >
              <g-image src="~/assets/fotosy/f4.jpg" width="500"/>
              </div></g-link>
            <h2 class="title" data-cta=" →">IV Faza</h2>
          </div>
          <div class="promo" style="--overlay-color: blue">
            <g-link to="/architektura-faza-5/">
            <div class="image-wrapper ruch" >
              <g-image src="~/assets/fotosy/f5.jpg" width="500"/>
              </div></g-link>
            <h2 class="title" data-cta=" →">V Faza</h2>
          </div>
                    </div> <!-- koniec menu2 -->


                    <div class="menu3"  v-show="submenu === 'historia'">
                    <div class="promo" style="--overlay-color: red">
                      <g-link to="/historia-powstanie-kosciola/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/Historia-powstanie-i-budowa.jpg" width="500"/>
                      </div></g-link>
                      <h2 class="title" data-cta=" →">Powstanie i budowa kościoła</h2>
                    </div>
                    <div class="promo" style="--overlay-color: orange">
                      <g-link to="/historia-pomnik-wdziecznosci/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/Historia-pomnik-wdziecznosci.jpg" width="500"/>
                      </div></g-link>
                      <h2 class="title" data-cta=" →">Pomnik wdzięczności</h2>
                    </div>
                    <div class="promo" style="--overlay-color: yellowgreen">
                      <g-link to="/historia-okres-siostr-brygidek/">
                      <div class="image-wrapper ruch">
                        <g-image src="~/assets/fotosy/Zabytki-okres-siostr-Brygidek.JPG" width="500"/>
                        </div></g-link>
                      <h2 class="title" data-cta=" →"> Okres Sióstr Brygidek</h2>
                    </div>
                    <div class="promo" style="--overlay-color: darkgreen">
                      <g-link to="/historia-okres-siostr-wizytek/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/Zabytki-okres-siostr-Wizytek.JPG" width="500"/>
                        </div></g-link>
                      <h2 class="title" data-cta=" →">Okres Sióstr Wizytek</h2>
                    </div>
                    <div class="promo" style="--overlay-color: blue">
                      <g-link to="/historia-koniec-wieku/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/Historia-koniec-wieku.JPG" width="500"/>
                        </div></g-link>
                      <h2 class="title" data-cta=" →">Koniec XIX wieku</h2>
                    </div>
                    <div class="promo" style="--overlay-color: darkgreen">
                      <g-link to="/historia-czasy-wspolczesne/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/Historia-czasy-wspolczesne.jpg" width="500"/>
                        </div></g-link>
                      <h2 class="title" data-cta=" →">Lubelskie Sanktuarium Pamięci Narodowej</h2>
                    </div>
                    <div class="promo" style="--overlay-color: yellowgreen">
                      <g-link to="/historia-wielka-renowacja/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/Historia-wielka-renowacja.JPG" width="500"/>
                        </div></g-link>
                      <h2 class="title" data-cta=" →">Wielka renowacja</h2>
                    </div>
                    <div class="promo" style="--overlay-color: orange">
                      <g-link to="/historia-ekspozycja-historyczna/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/ekspozycja historyczna.JPG" width="500"/>
                        </div></g-link>
                      <h2 class="title" data-cta=" →">Ekspozycja historyczna</h2>
                    </div>
                    <div class="promo" style="--overlay-color: red">
                      <g-link to="/historia-ekspozycja-archeologiczna/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/ekspozycja archeologiczna.JPG" width="500"/>
                        </div></g-link>
                      <h2 class="title" data-cta=" →">Ekspozycja archeologiczna</h2>
                    </div>
                    <div class="promo" style="--overlay-color: pink">
                      <g-link to="/historia-ekspozycja-numizmatyczna/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/ekspozycja numizmatyczna.JPG" width="500"/>
                        </div></g-link>
                      <h2 class="title" data-cta=" →">Ekspozycja numizmatyczna</h2>
                    </div>
                  </div> <!-- koniec menu3 -->



                    <div class="menu4"  v-show="submenu === 'zabytki'">
                    <div class="promo" style="--overlay-color: red">
                      <g-link to="/zabytki-okres-siostr-brygidek/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/Zabytki-okres-siostr-Brygidek.JPG" width="500"/>
                      </div></g-link>
                      <h2 class="title" data-cta="Zobacz Zabytki →">Okres Sióstr Brygidek</h2>
                    </div>
                    <div class="promo" style="--overlay-color: orange">
                      <g-link to="/zabytki-okres-siostr-wizytek/">
                      <div class="image-wrapper ruch" >
                        <g-image src="~/assets/fotosy/Zabytki-okres-siostr-Wizytek.JPG" width="500"/>
                      </div></g-link>
                      <h2 class="title" data-cta="Zobacz Zabytki →">Okres Sióstr Wizytek</h2>
                    </div>

                  </div> <!-- koniec menu4 -->
            </div><!-- koniec submenu -->

        </div><!-- koniec menusy -->
  </Layout>
</template>

<script>
  import { TimelineLite, TweenMax, gsap } from 'gsap';

  export default {
    mounted() {
      const loaderF = document.querySelector(".loaderF");
      gsap.to(loaderF, 1.6, {x: '-100%',}).to(loaderF, 1, {opacity: 0});
    },
    data() {
      return {
        submenu: ""
      }
    },
    methods: {
      pokaVfaz() {
        this.submenu = "Vfaz";
        const loaderMenu2 = document.querySelector(".menu2");
        const menuBig = document.querySelector(".menu");
        gsap.to(menuBig, 1.1, {x: '40%', opacity: 0, display: "none"});
        gsap.from(loaderMenu2, 1.1, {delay: 1.1, x: '-40%', opacity: 0})
        gsap.to(loaderMenu2, 1, {delay: 1.1, opacity: 1});
      },
      historia() {
        this.submenu = "historia";
        const loaderMenu2 = document.querySelector(".menu3");
        const menuBig = document.querySelector(".menu");
        gsap.to(menuBig, 1.1, {x: '40%', opacity: 0, display: "none"});
        gsap.from(loaderMenu2, 1.1, {delay: 1.1, x: '-40%', opacity: 0});
        gsap.to(loaderMenu2, 1, {delay: 1.1, opacity: 1});
      },
      zabytki() {
        this.submenu = "zabytki";
        const loaderMenu2 = document.querySelector(".menu4");
        const menuBig = document.querySelector(".menu");
        gsap.to(menuBig, 1.1, {x: '40%', opacity: 0, display: "none"});
        gsap.from(loaderMenu2, 1.1, {delay: 1.1, x: '-40%', opacity: 0});
        gsap.to(loaderMenu2, 1, {delay: 1.1, opacity: 1});
      },
      loaderGo() {

        const loader = document.querySelector(".loader");
        const menuBig = document.querySelector(".menu");

        gsap.to(loader, 1.6, {x: '-100%', opacity: 0});
        gsap.from(menuBig, 1.1, {delay: 1, x: '-30%', opacity: 0});

      }
    }


  }
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
.loader {
  width: 100%;
  height: 100%;
  position: fixed;
  top:0; left:0;
  background-color: #000;
  z-index: 1000;
  display: block;
}
.loaderF {
  width: 100%;
  height: 100%;
  position: fixed;
  top:0; left:0;
  background-color: #000;
  z-index: 1000000;
  display: block;
}



:root {
--src: url(https://images.unsplash.com/photo-1554620121-59e7f3f6e3a4?ixlib=rb-1.2.1&q=80&fm=jpg&crop=entropy);
--size: 55vmin;
--space: 15vmin;
--duration: 300ms;
--ease-out: cubic-bezier(0.25, 1, 0.5, 1);
--bounce-out: cubic-bezier(0.34, 1.56, 0.64, 1);

}

* {
box-sizing: border-box;
}

.menu, .menu2,  {
display: grid;
place-items: center;
grid-gap: var(--space);
margin: 0 auto;
padding: var(--space);
font-family: 'Conv_Ubuntu-LI';
color: white;
background-color: rgb(29, 30, 34);
/* background-color: #000); */

}
.submenu {
  /* z-index: -1; */
}
.menu, .submenu {
min-width: 32vw;

}
.menusy {
  display: flex;
}

.promo {
position: relative;
cursor: pointer;
width: var(--size);
height: var(--size);
/* filter: grayscale(50%); */
border-radius: 35% 65% 71% 29% / 49% 48% 52% 51%  ;

margin: var(--space);

}

.title {
--font-size: calc(var(--size) / 8);

display: flex;
align-items: center;
position: absolute;
left: 0;
bottom: 0;
font-size: var(--font-size);
font-weight: 700;
line-height: 1.2;
white-space: nowrap;
transform: translate(-10%, -50%);
transition: transform var(--duration) var(--ease-out);
pointer-events: none;
color: #fff;
}

.title::after {
content: attr(data-cta);
display: inline-block;
margin-left: 1.5vmin;
font-size: calc(var(--font-size) / 3.25);
font-weight: 400;
letter-spacing: 0.125vmin;
opacity: 0;
transform: translateX(-25%);
transition: transform var(--duration) var(--ease-out),
opacity var(--duration) var(--ease-out);
}

.image-wrapper {
width: var(--size);
height: var(--size);
overflow: hidden;
clip-path: polygon(100% 0, 100% 50%, 100% 100%, 0% 100%, 0 50%, 0% 0%);
transition: transform var(--duration) var(--ease-out),
clip-path var(--duration) var(--ease-out);

clip-path: polygon(75% 0%, 100% 50%, 75% 100%, 0% 100%, 25% 50%, 0% 0%);
transform: translateX(25%);
transition-timing-function: var(--bounce-out);


}

.image-wrapper img {
position: relative;
width: 120%;
height: 100%;
object-fit: cover;
transform: translateX(-10%);
transition: transform var(--duration) var(--ease-out);
/* border-radius: 35% 65% 71% 29% / 49% 48% 52% 51%  ; */


}

.image-wrapper::after {
content: "";
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
background-color: var(--overlay-color);
mix-blend-mode: multiply;
opacity: 0;
transform: translateZ(0);
transition: opacity var(--duration) var(--ease-out);
}

.promo:hover img {
transform: translateX(0);
}

.promo:hover .image-wrapper {
clip-path: polygon(75% 0%, 100% 50%, 75% 100%, 0% 100%, 25% 50%, 0% 0%);
transform: translateX(25%);
transition-timing-function: var(--bounce-out);
}

.promo:hover .title {
transform: translate(5%, -50%);
transition-timing-function: var(--bounce-out);
}

.promo:hover .title::after {
opacity: 1;
transform: translateX(0);
transition-timing-function: var(--bounce-out);
}

.promo:hover .image-wrapper::after {
opacity: 1;
}
.promo:hover {
/* filter: grayscale(0); */

}

/* @media screen  and (orientation: portrait) {
  h3 {
    font-size: 1.4rem;
    z-index: 44;
    padding: 10vh 0;
  }
  a, ul, ol, p {
      color: #fff;
      max-width: 90vw;
      font-size: 1.2em;
      padding: 10vh 0;
      line-height: 1.1em;
  }
}
@media screen  and (orientation: landscape) {
  h3 {
    font-size: 2.4rem;
    position: relative;
    top: 30vh;
    z-index: 44;
    padding-left: 10vw;
    margin-top: -20vh;
  }
  a, ul, ol, p {
      color: #fff;
      max-width: 75vw;
      font-size: 1.6em;
      overflow: hidden;
      padding: 10vh 0;
      line-height: 1.4em;
  }
  img.small {
    width: 40%;
  }
} */


</style>
