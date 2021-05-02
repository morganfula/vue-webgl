<template>
  <div class="animation">
    {{ page }}
  </div>
</template>

<script>
import { mapState } from "vuex";
import * as THREE from "three";
import { TimelineMax } from "gsap";
var OrbitControls = require("three-orbit-controls")(THREE);

export default {
  data() {
    return {
      state: [],
      material: {},
      geometry: {}
    };
  },
  computed: mapState(["page"]),
  watch: {
    page: function(newValue, oldValue) {
      let tl = new TimelineMax({
        onComplete: function() {}
      });
    }
  },
  mounted() {
    let camera, controls, scene, renderer, geometry, material;

    let vm = this;

    function init() {
      // Scene
      scene = new THREE.Scene();

      // Objects
      // Material
      material = new THREE.MeshBasicMaterial({ color: 0xff0000 });
      material.wireframe = true;

      geometry = new THREE.BoxGeometry();

      const mesh = new THREE.Mesh(geometry, material);
      scene.add(mesh);

      //  Renderer
      renderer = new THREE.WebGLRenderer();
      renderer.setPixelRatio(window.devicePixelRatio);
      renderer.setSize(window.innerWidth, window.innerWidth);

      const container = vm.$el;
      container.appendChild(renderer.domElement);

      /**
       * Camera
       */
      camera = new THREE.PerspectiveCamera(
        70,
        window.innerWidth / window.innerHeight,
        0.001,
        500
      );
      camera.position.set(0, 0, 4);

      // Controls
      controls = new OrbitControls(camera, renderer.domElement);
      resize();
    }

    function resize() {
      var w = window.innerWidth;
      var h = window.innerHeight;
      renderer.setSize(w, h);
      camera.aspect = w / h;
      camera.updateProjectionMatrix();
    }

    let time = 0;
    function animate() {
      time++;

      requestAnimationFrame(animate);
      render();
    }

    function render() {
      renderer.render(scene, camera);
    }

    init();
    animate();
  }
};
</script>

<style lang="scss" scoped>
.animation {
  position: fixed;

  width: 200px;
  height: 20px;
  background: red;
}
</style>
