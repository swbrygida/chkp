<template id="">
  <div class="counter2">
  <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css" integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/" crossorigin="anonymous">



  <div class="arr">
  <i class="znik fas fa-angle-double-down" @click="dodaj"></i>
</div>
  <div class="arr">
  <div class="sekcje"><span>POZIOM</span> {{ktorypoziom}} <br>{{slajd}}/{{slajdy}}</div>
</div>

  <div class="arr">
  <i class="znik fas fa-angle-double-up" @click="odejmij"></i>
</div>
<a href="/menu/">
<i class="menuIcon fas fa-solid fa-bars"></i>
</a>



  </div><!-- koniec counter -->

</template>
<script>
import { TimelineLite, TweenMax, gsap } from 'gsap';

export default {
  props: ['clicker', 'allSections', 'level2', 'level3'],
  data() {
    return {
      ktorypoziom: 1,
      slajd: 1,
      slajdy: 1
    }
  },
  mounted() {

    let ileslajdow = this.level2 - 1;
    this.slajdy = ileslajdow;
  },
  methods: {
    dodaj() {
     gsap.to('.znik', 0.1, {opacity: 0, display: "none"});
     if (this.clicker < this.allSections) {

         this.$emit('clicker', this.clicker++);
         let numberX = this.clicker;
         let numberXS = numberX -1;
         let numberPS = 'section:nth-child(' + numberXS + ')';
         let numberPN = 'section:nth-child(' + numberX + ')';
         let loader1 = document.querySelector(numberPS)
         let loader2 = document.querySelector(numberPN)
         gsap.to(loader1, { y: '-40%', opacity: 0, display: "none"});
         gsap.from(loader2, 1.6, {delay: 1.6, display: "block", y: '40%', opacity: 0, });
         gsap.to(loader2, 1.6, {delay: 0.6,  scrollTo: {y: -200} });
         gsap.to(loader2, 1.6, {delay: 2.6,  display: "block",  backgroundColor: '#000', color: '#fff'});
};
if (this.clicker < this.level2){
  this.slajd = this.clicker;
} else if (this.clicker >= this.level2 && this.clicker < this.level3) {
  this.ktorypoziom = 2;
  this.slajdy = this.level3 - this.level2;
  this.slajd = this.clicker -this.level2 + 1;
} else if (this.clicker >= this.level3) {
  this.ktorypoziom = 3;
  this.slajdy = this.allSections - this.level3 +1;
  this.slajd = this.clicker -this.level3 + 1;
};
gsap.from('.znik', 0.2, {delay: 3.6, opacity: 0, display: "block"});



    },
    odejmij() {

           if (this.clicker > 1) {
      this.$emit('clicker', this.clicker--);
      let numberXW = this.clicker + 1;
      let numberPW = 'section:nth-child(' + numberXW + ')';
      let numberXWZ = this.clicker;
      let numberPWZ = 'section:nth-child(' + numberXWZ + ')';

      let load = document.querySelector(numberPW);
      let load2 = document.querySelector(numberPWZ);

      gsap.to(load, {y: '100%', opacity: 0, display: "none" });
      gsap.from(load2, 0.6, {delay: 0.6, display: "block", y: '-100%', opacity: 0, });
      gsap.to(load2, 0.6, { delay: 1.6, display: "block",  y: '0', opacity: 1, backgroundColor: '#000', color: '#fff'});
};
if (this.clicker < this.level2){
  this.slajd = this.clicker;
  this.ktorypoziom = 1;
  this.slajdy = this.level2 -1;
} else if (this.clicker >= this.level2 && this.clicker < this.level3) {
  this.ktorypoziom = 2;
  this.slajdy = this.level3 - this.level2;
  this.slajd = this.clicker -this.level2 + 1;
} else if (this.clicker >= this.level3) {
  this.ktorypoziom = 3;
  this.slajdy = this.allSections - this.level3 +1;
  this.slajd = this.clicker -this.level3 + 1;
};



  }
}
}
</script>
<style scoped>
@media screen  and (orientation: portrait) {
  .counter2 {
  margin: 0 ;
  padding: 1vh 0;
  width: 100vw;
  height: 30vh;
  display: flex;
  justify-content: space-around;
  position: fixed;
  bottom: 0;
  right: 0;
  max-height: 19vw;
  background: #333;

  }
  .sekcje {
    font-size: 0.6em;
    margin: 2vh 0 0 0;
    color: gray;
  }
  .sekcje span {
    font-size: 0.4em;
  }
}

@media screen  and (orientation: landscape) {
  .counter2 {
  margin: 0 ;
  padding: 1vh 0;
  width: 48vh;
  height: 11vh;
  display: flex;
  justify-content: space-between;
  position: fixed;
  bottom: 0;
  right: 0;
  background: #333;

  }
  .sekcje {
    font-size: 0.8em;
    margin: -8vh 0 0 0 ;
    color: gray;
    padding: 8vh 0 0 0;
    line-height: 1.2em;

  }
  .sekcje span {
    font-size: 0.4em;
  }
}


.arr, a {
  width: 11vh;
  height: 11vh;
  padding: 1vh 1vw;
  text-align: center;
  font-size: 1.9em;
  padding:0;
  background: #333;
  /* border-radius: 50%; */

  color: #666;
  transition: .5s;

}



a:hover, .arr:hover {
color: #ffee10;
box-shadow: 0 0 5px #ffee10;
text-shadow: 0 0 5px #ffee10;
}

.znik, .menuIcon {
  width: 100%;
  height: 100%;
  padding: 3vh 0 ;
}


</style>
