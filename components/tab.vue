<template>
  <img src="../static/icons/index.png" class="icon" id="1" />
</template>

<script>
import defaultVue from "../layouts/default.vue";

export default {
  props: ["tabId", "source"],
  data: function () {
    return {
      tId: this.tabId,
      srce: this.source,
    };
  },
  mounted: function () {
    //document.getElementById(1).src=this.source;
    document.getElementById("1").id = this.tabId;

    //   document
    //     .getElementById(this.tabId)
    //     .addEventListener("mouseenter", this.mouseOnTab);
    //   document
    //     .getElementById(this.tabId)
    //     .addEventListener("mouseleave", this.mouseNotTab);
    //   document
    //     .getElementById(this.tabId)
    //     .addEventListener("click", this.mouseClick);

    //     switch (this.tabId) {
    //     case "1" :{
    //     this.selected="index";
    //     break;}
    //     case "2" :{
    //     this.selected="profile";
    //     break;}
    //     case "3" :{
    //     this.selected="skills";
    //     break;}
    //     case "4" :{
    //     this.selected="projects";
    //     break;}
    //     case "5" :{
    //     this.selected="contact";
    //     break;}
    //   default:this.selected="contact";
    //     break;}

   // document.getElementById(this.tabId).src =  "/_nuxt/static/icons/" + this.source + ".png";
  },
  methods: {
    // mouseClick(e) {
    //       if(this.selected!="index")
    //       this.$router.push('/'+this.selected);
    //       else
    //       this.$router.push('/');
    //  },
  },
};
</script>

<style></style>
