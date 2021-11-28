<template>
  <div class="layout">

    <slot/>
  </div>
</template>



<style>
@import url('https://fonts.googleapis.com/css2?family=Exo+2:ital,wght@0,300;1,800&family=Inknut+Antiqua:wght@800&family=Libre+Baskerville:ital@1&display=swap');

@font-face {
	font-family: 'Conv_Ubuntu-LI';
	src: url('../assets/fonts/Ubuntu-LI.eot');
	src: local('☺'), url('../assets/fonts/Ubuntu-LI.woff') format('woff'),
  url('../assets/fonts/Ubuntu-LI.ttf') format('truetype'),
  url('../assets/fonts/Ubuntu-LI.svg') format('svg');
	font-weight: normal;
	font-style: normal;
}
h1, h2, h3, h4 {
  font-family: 'Inknut Antiqua', serif;

}

body {
    font-family:  'Conv_Ubuntu-LI', sans-serif;
    /* font-family: 'Exo 2', sans-serif; */
    /* font-family: 'Libre Baskerville', serif; */
    font-weight: normal;
    font-style: normal;
    margin: 0;
    padding: 0;
    border: 0;
    background-color: #000;
    display: flex;
    flex-direction: column;

    min-height: 110vh;



}

section {
  display: none;
  min-height: 110vh;
  max-width: 100vw;
  overflow: hidden;

}
.figure {
  overflow: hidden;
  width: 99vw;
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
  display: block;
  position: relative;
}
.figure:before {
  box-shadow: inset 1vh 1vw 12vw 7vw rgba(0, 0, 0, 0.9);
  content: "";
  height: 100%;
  position: absolute;
  width: 100%;
}
img {
  width: 100%;
}
img:hover {
transform: scale(1.1,1.1) rotate(1deg);
transition: all 50s;
}
@media screen  and (orientation: portrait) {

  h3 {
    font-size: 1.1rem;
    z-index: 44;
    padding: 3vh 0;
  }
  a, ul, ol, p {
      color: #fff;
      max-width: 90vw;
      font-size: 1.2em;
      padding: 10vh 2vw;
      line-height: 1.1em;
  }
  .brygida_logo {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 99vw;
    height: 99vh;

  }
  .brygida_logo img {
    height: 65%;
    max-width: 80%;
  }
}
@media screen  and (orientation: landscape) {
  h3 {
    font-size: 2.4rem;
    position: relative;
    top: 30vh;
    z-index: 44;
    padding: 0 5vw;
    margin-top: -20vh;
  }
  a {
      color: #fbfbfb;
      max-width: 75vw;
  }
  ul, ol {
      color: #fbfbfb;
      max-width: 70vw;
      font-size: 1.9em;
      overflow: hidden;
      margin: 3vh 14vw;
      padding: 1vh 1vw;
      line-height: 1.9em;
  }
  p {
      color: #fbfbfb;
      max-width: 70vw;
      font-size: 1.9em;
      overflow: hidden;
      margin: 3vh 14vw;
      padding: 1vh 1vw;
      line-height: 1.9em;
  }
  .brygida_logo {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .brygida_logo img {
    max-width: 35%;
    max-height: 90%;
  }
  img.small {
    width: 40%;
  }
  .onme {
    margin-bottom: -450px;
    z-index: -1;
  }
}
</style>
