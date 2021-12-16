<template id="">
  <div class="counter2">
  <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css" integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/" crossorigin="anonymous">




  <div class="arr">
  <!-- <div class="sekcje" @click="poziomy = !poziomy"><span>POZIOM</span> {{ktorypoziom}} <br>{{slajd}}/{{slajdy}}</div> -->


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
      slajdy: 1,
      poziomy: false
    }
  },
  mounted() {

    let ileslajdow = this.level2 - 1;
    this.slajdy = ileslajdow;
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
  cursor: pointer;
}
.poziomy {
  position: relative;
  top: -21vh;
  background-color: #333;
  animation: poka 0.6s;
}
.poziomy p {
  font-size: 0.8em!important;
  line-height: 1em;
  margin: 0;
  padding: 0;
  color: #666;
}
.poziomy p:hover {
  color: #ffee10;
  box-shadow: 0;
  text-shadow: 0;
  cursor: pointer;
}
.poziomy p span {
  font-size: 0.4em;
}
@keyframes poka {
  from {opacity: 0;}
  to {opacity: 1;}
}
</style>
