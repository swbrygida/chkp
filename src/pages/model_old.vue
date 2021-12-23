<template>
  <Layout>



    <div class="counter2">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css" integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/" crossorigin="anonymous">
  <div class="arr">
    <!-- <div class="sekcje" @click="poziomy = !poziomy"><span>POZIOM</span> {{ktorypoziom}} <br>{{slajd}}/{{slajdy}}</div> -->
  </div>
  <a href="/menu/" @click="removeChild">
  <i class="menuIcon fas fa-solid fa-bars"></i>
</a>




    </div><!-- koniec counter -->
  </Layout>
</template>
<script>
import { TimelineLite, TweenMax, gsap } from 'gsap';
import * as THREE from 'three';



import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js';
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js";
import { RGBELoader } from "three/examples/jsm/loaders/RGBELoader.js";
import { OBJLoader } from "three/examples/jsm/loaders/OBJLoader.js";

export default {
  methods: {
    removeChild() {
      let model = document.getElementsByClassName("model");
      gsap.to(model, 0.6, { opacity: 0, display: "none"});
    }
  },
  mounted() {
    let camera, scene, renderer;

        init();
        render();

        function init() {
          const container = document.createElement("div");
          document.body.appendChild(container);
          container.className = "model";

          camera = new THREE.PerspectiveCamera(
            45,
            window.innerWidth / window.innerHeight,
            0.25,
            20
          );
          camera.position.set(-9, 8.6, 4.7);

          scene = new THREE.Scene();
          const light2 = new THREE.PointLight( 0xff0000, 1, 100 );
  light2.position.set( 50, 50, 50 );
  scene.add( light2 );
  const light3 = new THREE.PointLight( 0xffff00, 1, 100 );
  light3.position.set( 0, -20, -80 );
  scene.add( light3 );



          // const light = new THREE.AmbientLight( 0x404040 ); // soft white light
          // scene.add( light );
          const directionalLight = new THREE.DirectionalLight( 0xffffff, 0.5 );
  scene.add( directionalLight );

          new RGBELoader()
            .setDataType(THREE.UnsignedByteType)
            .setPath("/modele/")
            .load("multi.hdr", function (texture) {
              const envMap = pmremGenerator.fromEquirectangular(texture).texture;

              scene.background = envMap;
              scene.environment = envMap;

              texture.dispose();
              pmremGenerator.dispose();

              render();

              // model

              const loader = new GLTFLoader().setPath("/modele/");
              loader.load("church.glb", function (gltf) {
                scene.add(gltf.scene);

                render();
              });
            });

          renderer = new THREE.WebGLRenderer({ antialias: true });
          renderer.setPixelRatio(window.devicePixelRatio);
          renderer.setSize(window.innerWidth, window.innerHeight);
          renderer.toneMapping = THREE.ACESFilmicToneMapping;
          renderer.toneMappingExposure = 1;
          renderer.outputEncoding = THREE.sRGBEncoding;
          container.appendChild(renderer.domElement);

          const pmremGenerator = new THREE.PMREMGenerator(renderer);
          pmremGenerator.compileEquirectangularShader();

          const controls = new OrbitControls(camera, renderer.domElement);
          controls.addEventListener("change", render); // use if there is no animation loop
          controls.minDistance = 5;
          controls.maxDistance = 15;
          controls.target.set(0, 0, -0.2);
          controls.update();
        }

        //

        function render() {
          renderer.render(scene, camera);
        };



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
