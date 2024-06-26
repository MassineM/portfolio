<template>
  <div>
    <div id="particleCont">
      <!-- <vue-particles
        color="#432a92"
        :particleOpacity="0.3"
        :particlesNumber="30"
        shapeType="circle"
        :particleSize="9"
        linesColor="#9b8ccc"
        :linesWidth="2"
        :lineLinked="true"
        :lineOpacity="0.15"
        :linesDistance="400"
        :moveSpeed="1"
        :hoverEffect="false"
        :clickEffect="false"
        class="particles"
      >
      </vue-particles> -->
      <particles class="particles" />
    </div>
    <!-- <div class="bodyPage"> -->
    <sidemenu id="sideMenu" />
    <main>
      <Nuxt />
    </main>
    <!-- </div> -->
  </div>
</template>

<script>
import particles from "../components/particles.vue";
export default {
  components: { particles },
  methods: {},
  mounted: function () {
    document.getElementById("particleCont").style.opacity = 1;
    setTimeout(function () {
      document.getElementById("sideMenu").style.opacity = 1;
      document.getElementById("sideMenu").style.transform = "translateX(0%)";
    }, 4000);
  },
};
</script>

<style>
#sideMenu {
  opacity: 0;
  transform: translateX(-100%);
  transition: all 1s ease-in-out;
}
#particleCont {
  opacity: 0;
  transition: all 2s ease-in-out;
}
</style>
