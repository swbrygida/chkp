<template>
  <Layout>

    <Arrows2

       />
  </Layout>
</template>
<script>
import { TimelineLite, TweenMax, gsap } from 'gsap';
import * as THREE from 'three';
import Arrows2 from '~/components/Arrows2.vue';


import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js';
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js";
import { RGBELoader } from "three/examples/jsm/loaders/RGBELoader.js";
import { OBJLoader } from "three/examples/jsm/loaders/OBJLoader.js";

export default {
  components: {
  Arrows2
  },
  mounted() {
    let camera, scene, renderer;

        init();
        render();

        function init() {
          const container = document.createElement("div");
          document.body.appendChild(container);

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
              loader.load("church2.glb", function (gltf) {
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
<style>

</style>
