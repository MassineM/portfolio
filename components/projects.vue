<template>
  <div id="projects">
    <div class="mainArticle">
      <h1 class="title">Some of my previous works:</h1>
      <ul class="container"><li
        v-for="tab of projects"
        v-html="tab.title"
        :id="`tab_${tab.key}`"
        :key="tab.key"
        class="project"
        :class="{ active: tab.selected }"
        @click="selectTab(tab)"
      ></li></ul>
      <table>
        <tr>
          <td class="text">Name</td>
          <td class="text" v-html="`${selectedTab.title}`" />
        </tr>
        <tr>
          <td class="text">Description</td>
          <td class="text" v-html="`${selectedTab.description}`" />
        </tr>
        <tr>
          <td class="text">Tools used</td>
          <td class="text" v-html="`${selectedTab.tools}`" />
        </tr>
        <tr>
          <td class="text">Link</td>
          <td class="text" v-html="`${selectedTab.link}`" />
        </tr>
        <tr>
          <td class="text">Year</td>
          <td class="text" v-html="`${selectedTab.year}`" />
        </tr>
      </table>
      
    </div>
  </div>
</template>

<script>
//document.addEventListener('mousemove',function(e){mypageY=e.pageY;});
export default {
  data: function(){
    return{
      selTitle:"test",
      selectedTab:{},
      projects: [
        {
          key: 1,
          title: "This WEB portfolio",
          description: "Personnal project made from scratch, firstly in the purpose of publishing an accessible Curriculum Vitae, before the ambition of completing a rich portfolio took over.",
          tools: "Nuxt.JS based, icons using Illustrator, background using Photoshop, SASS for animations, mainly structured by Vue.JS and JavaScript.",
          link: "http://www.snek-france.fr/",
          year: 2022,
          selected: true,
        },
        {
          key: 2,
          title: "Snek",
          description: "Based on the classic snake game concept, this is a home made version with variable levels and maps, hosted on an adapted Web platform.",
          tools: "Nuxt.JS and Vue for the front, Node.JS for the API, connected to MongoDB and containing the Unity game launcher under WebGL.",
          link: "http://www.snek-france.fr/projects/snek",
          year: 2021,
          selected: false,
        },
        {
          key: 3,
          title: "Connect 4",
          description: "Visual interface game made including player vs computer",
          tools: "Mainly object-oriented using Java and JavaFX for graphics.",
          link: "http://www.snek-france.fr/projects/connect4",
          year: 2021,
          selected: false,
        },
        {
          key: 4,
          title: "Space Invaders",
          description: "Visual interface space shooter game",
          tools: "Mainly object-oriented using Java and JavaFX for graphics.",
          link: "http://www.snek-france.fr/projects/invaders",
          year: 2020,
          selected: false,
        },
        {
          key: 5,
          title: "Truck Platooning",
          description: "Supervised personal initiative work as a part of the preparatory classes for engineering schools contests.",
          tools: "Research and study of functionnal & technical aspects of platooning technologies on heavy vehicles.",
          link: "http://www.snek-france.fr/projects/platooning",
          year: 2019,
          selected: false,
        },
        {
          key: 6,
          title: "Dodger Cab",
          description: "First ever self-made game and developped program from scratch, dodge police cars and beat your own highscore.",
          tools: "Python 3 and Pygame library",
          link: "http://www.snek-france.fr/projects/dodger",
          year: 2012,
          selected: false,
        },
      ],
    }
  },
  mounted:function(){
    this.selectedTab =this.projects[0];

  },
  methods: {
    selectTab(tab){
      this.selectedTab=tab;
      for(const each of this.projects){
        each.selected=false;
      }
      tab.selected=true;
    }

  },
};
</script>
<style lang="scss" scoped></style>
