<template>
  <div class="pagemodel">
    <div class="stickyBanner" id="banner">
      <tab v-for="I in items" :key="I.Id" :tabId="I.Id" :source="I.Sc" />
      <div id="shadow" class="shadow" style="top: 0px">
        <h1 id="selectedTab" style="opacity: 0"></h1>
      </div>
      <div id="shadowCurr" class="shadow"></div>
    </div>
    <Nuxt />
  </div>
</template>

<script>
import tab from "../components/tab.vue";

export default {
  components: { tab },
  mounted: function () {
    window.addEventListener("mousemove", this.mouseIsMoving);
    document
      .getElementById("banner")
      .addEventListener("mouseover", this.mouseOnBanner);
    document
      .getElementById("banner")
      .addEventListener("mouseout", this.mouseNotBanner);
    this.onBanner = false;
    this.onTab = false;
    for (let i = 1; i <= 5; i++) {
      document
        .getElementById(i)
        .addEventListener("mouseenter", this.mouseOnBanner);
      document
        .getElementById(i)
        .addEventListener("mouseleave", this.mouseNotTab);
      document.getElementById(i).addEventListener("click", this.mouseClick);
    }
  },
  methods: {
    mouseIsMoving(e) {
      this.vw = Math.max(
        document.documentElement.clientWidth || 0,
        window.innerWidth || 0
      );
      this.vh = Math.max(
        document.documentElement.clientHeight || 0,
        window.innerHeight || 0
      );
      // console.log(e.pageY);
      var xPercent = e.pageX / this.vw;
      var yPercent = e.pageY / this.vh;

      if (!this.onBanner && !this.onTab) {
        document.getElementById("shadow").style.opacity = 0.7 - xPercent;
        document.getElementById("shadow").style.top =
          Math.floor(e.pageY / 1) * 1 + "px";
      }
      // console.log(vw);
      // console.log(e.pageX);
      //this.last_mouse_position = e.pageY;
    },
    mouseOnBanner(e) {
      switch (this.closest) {
        case 1: {
          this.selected = "index";
          break;
        }
        case 2: {
          this.selected = "profile";
          break;
        }
        case 3: {
          this.selected = "skills";
          break;
        }
        case 4: {
          this.selected = "projects";
          break;
        }
        case 5: {
          this.selected = "contact";
          break;
        }
        default:
          this.selected = "index";
          break;
      }

      // console.log( document.getElementById("tab" + this.currTab).offsetTop+2.5*this.vh/100);
      // console.log( this.currTab);
      // console.log( this.closest);

      document.getElementById("selectedTab").innerText = this.selected;
      document.getElementById("selectedTab").style.opacity = 1;

      this.onBanner = true;
      var c = 2000;
      for (let i = 1; i <= 5; i++) {
        if (
          Math.abs(
            document.getElementById(i).offsetTop +
              (2.5 * this.vh) / 100 -
              e.pageY
          ) < c
        ) {
          c = Math.abs(
            document.getElementById(i).offsetTop +
              (2.5 * this.vh) / 100 -
              e.pageY
          );
          this.closest = i;
        }
      }
      document.getElementById("shadow").style.top =
        document.getElementById(this.closest).offsetTop +
        (2.5 * this.vh) / 100 +
        "px";
      document.getElementById("selectedTab").style.opacity = 1;
      document.getElementById("shadow").style.width = "500%";
      
      document.getElementById("shadow").style.opacity = 1;
    },
    mouseNotBanner(e) {
      this.onBanner = false;
      document.getElementById("shadow").style.width = "100%";
      document.getElementById("selectedTab").style.opacity = 0;
    },
    mouseNotTab(e) {
      this.onTab = false;
    },
    mouseClick(e) {
      if (this.selected != "index") this.$router.push("/" + this.selected);
      else this.$router.push("/");

      switch (this.selected) {
        case "index": {
          this.currTab = 1;
          break;
        }
        case "profile": {
          this.currTab = 2;
          break;
        }
        case "skills": {
          this.currTab = 3;
          break;
        }
        case "projects": {
          this.currTab = 4;
          break;
        }
        case "contact": {
          this.currTab = 5;
          break;
        }
        default:
          this.currTab = 1;
          break;
      }

      document.getElementById("shadowCurr").style.top =
        document.getElementById(this.currTab).offsetTop +
        (2.5 * this.vh) / 100 +
        "px";
      for (let i = 1; i <= 5; i++) {
        if (this.currTab == i)
          document.getElementById(i).style.filter = "saturate(600%)";
        else document.getElementById(i).style.filter = "saturate(100%)";
      }
    },
  },
  data() {
    return {
      items: [
        { Id: "2", Sc: "profile" },
        { Id: "3", Sc: "skills" },
        { Id: "4", Sc: "projects" },
        { Id: "5", Sc: "contact" },
        { Id: "1", Sc: "profile" },
      ],
    };
  },
};
</script>

<style>
.shadow {
  transition: top 0.2s ease-out, opacity 0.2s ease-out, width 0.2s ease-out;
}
</style>
