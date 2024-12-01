<template>
  <section id="Projects" class="mainArticle">
    <h1 class="title">Previous projects</h1>
    <ul class="container">
      <li
        v-for="tab of projects"
        v-html="tab.title"
        :id="`tab_${tab.key}`"
        :key="tab.key"
        class="project"
        :class="{ active: tab.selected }"
        @click="selectTab(tab)"
      ></li>
    </ul>
    <div style="height: 33vh">
      <Transition name="slidefade">
        <table v-if="show" class="pTable">
          <tr class="pLign">
            <td class="pTitle pTop pLeft">Name</td>
            <td class="pItem pTop pRight">{{ selectedTab.name }};</td>
          </tr>
          <tr class="pLign">
            <td class="pTitle pLeft">Description</td>
            <td class="pItem pRight">{{ selectedTab.description }};</td>
          </tr>
          <tr class="pLign">
            <td class="pTitle pLeft">Skills</td>
            <td class="pItem pRight">{{ selectedTab.tools }};</td>
          </tr>
          <tr class="pLign" v-if="selectedTab.link">
            <td class="pTitle pLeft">Source code</td>
            <td class="pItem pRight">
              <a :href="`${selectedTab.link}`" target="_blank"
                >{{ selectedTab.link }};</a
              >
            </td>
          </tr>
          <tr class="pLign">
            <td class="pTitle pLeft pDown">Year</td>
            <td class="pItem pRight pDown">{{ selectedTab.year }};</td>
          </tr>
        </table>
      </Transition>
    </div>
    <a
      target="_blank"
      class="documentation"
      href="https://drive.google.com/drive/folders/1YxnYqCPUNngOJvELSOoJQK2760Orkcsb?usp=sharing"
      ><span v-html="link2"> </span>For all available documentation, click
      here.</a
    >
    <p class="moreCodes">
      Check out my GitHub below<br />
      for more projects' source codes
    </p>
  </section>
</template>

<script>
export default {
  data: function () {
    return {
      link2:
        '<svg xmlns="http://www.w3.org/2000/svg" id="OBJECT" viewBox="0 0 512 512"><defs><style>.cls-2{fill:#3d9ae2}.cls-3{fill:#fff}</style></defs><path fill="#bddbff" d="M431 432.75H269l-188 35V47.5a40 40 0 0 1 40-40h310Z"/><path d="M81 475.25a7.5 7.5 0 0 1-7.5-7.5V47.5A47.56 47.56 0 0 1 121 0h310a7.5 7.5 0 0 1 7.5 7.5v425.25a7.5 7.5 0 0 1-7.5 7.5H269.69L82.37 475.12a7 7 0 0 1-1.37.13ZM121 15a32.54 32.54 0 0 0-32.5 32.5v411.22l179.13-33.34a7 7 0 0 1 1.37-.13h154.5V15Z" class="cls-2"/><path d="M395.42 467.75A36.75 36.75 0 0 1 431 431H117.75A36.75 36.75 0 0 0 81 467.75a36.75 36.75 0 0 0 36.75 36.75H431a36.75 36.75 0 0 1-35.58-36.75Z" class="cls-3"/><path d="M431 512H117.75a44.25 44.25 0 0 1 0-88.5H431a7.52 7.52 0 0 1 .24 15 29.23 29.23 0 0 0 0 58.44 7.52 7.52 0 0 1-.24 15Zm-313.25-73.5a29.25 29.25 0 0 0 0 58.5h281.12a44.54 44.54 0 0 1 0-58.5Z" class="cls-2"/><rect width="240" height="120" x="136" y="81" class="cls-3" rx="20" ry="20"/><path d="M356 208.5H156a27.54 27.54 0 0 1-27.5-27.5v-80A27.54 27.54 0 0 1 156 73.5h200a27.54 27.54 0 0 1 27.5 27.5v80a27.54 27.54 0 0 1-27.5 27.5Zm-200-120a12.52 12.52 0 0 0-12.5 12.5v80a12.52 12.52 0 0 0 12.5 12.5h200a12.52 12.52 0 0 0 12.5-12.5v-80A12.52 12.52 0 0 0 356 88.5Z" class="cls-2"/></svg>',
      selectedTab: {},
      show: false,
      projects: [
        {
          key: 1,
          title: "PM<br />@ MajorMedia",
          name: "Project Manager at MajorMedia",
          description:
            "Managing clients' projects & applications. My responsibilities include planning the team's workload and helping them achieve their goals, managing clients and defining their needs, defining the offer based on their objective and budget, proxy product owner and quality assurance tasks, and more...",
          tools:
            "PM | PPO | QA | React.JS | Next.JS |Laravel | PHP | October CMS | WordPress | PrestaShop | ClickUp | GitHub | Figma | Agile methods",
          year: 2024,
          selected: true,
        },
        {
          key: 2,
          title: "Internship <br /> @ Sopra Steria",
          name: "Internship at Sopra Steria",
          description:
            "As a Front-End developers team member on the SNCF’s TER website, France’s regional railways app, I did some maintenance work, features and tests creation, as well as improving accessibility",
          tools:
            "React | Next.JS | TypeScript | Jest | Jira | GitLab | Jenkins | Docker | Web accessibility | Agile methods | SCRUM",
          year: 2023,
          selected: true,
        },
        {
          key: 3,
          title: "Internship <br /> @ Fonaco",
          name: "Internship at Fonaco",
          description:
            "Developing a showcase website and an agency management platform, as well as working with clients doing graphic design and printing on various supports",
          tools:
            "Vue.JS | JavaScript | PHP | MySQL | Adobe Illustrator | Photoshop | Premiere Pro",
          link: "https://github.com/MassineM/FonacoGestionPHP",
          year: 2022,
          selected: false,
        },
        {
          key: 4,
          title: "PlantIO",
          name: "PlantIO",
          description:
            "This project's goal is to help any farmer or gardner understand their plantations' environment to promote optimal growth conditions",
          tools:
            "Setting a Raspberry to collect data for a Firebase API, consumed by a web front (Angular) & mobile app (React)",
          link: "https://github.com/MassineM/PlantIO",
          year: 2023,
          selected: false,
        },
        {
          key: 5,
          title: "AMLBID Interface <br /> & AutoML Research",
          name: "AMLBID Interface & AutoML Research",
          description:
            "Improving and adding features to a user interface of an automated machine learning system. Another part of the project is a bibliographic research on Automated Machine Learning",
          tools:
            "Adding dynamic features in PHP to a Wordpress website, and connecting it to the Flask - Python generated AML system. Research based on scientific articles made with LaTeX",
          year: 2023,
          selected: false,
        },
        {
          key: 6,
          title: "Connected Hive",
          name: "Connected Hive",
          description:
            "Part of a bigger project, the main task was to create a bee farm data exploiting web platform",
          tools:
            "Data gathering: Arduino & Sigfox, API: Node.JS & MongoDB, APP: NuxtJS, Vue and Vuetify",
          link: "https://github.com/MassineM/connectedHive",
          year: 2022,
          selected: false,
        },
        {
          key: 7,
          title: "Snek",
          name: "Snek",
          description:
            "Based on the classic snake game concept, this is a home made version with variable levels and maps, hosted on an adapted Web platform",
          tools:
            "Nuxt.JS and Vue for the front, Node.JS for the API, connected to MongoDB and containing the Unity game launcher under WebGL",
          link: "https://github.com/MassineM/Snek",
          year: 2021,
          selected: false,
        },
        // {
        //   key: 7,
        //   title: "Dodger Cab",
        //   name: "Dodger Cab",
        //   description:
        //     "First ever self-made game and developped program from scratch, dodge police cars and beat your own highscore",
        //   tools: "Python 3 and Pygame library",
        //   link: "https://github.com/MassineM/dodgerCab",
        //   year: 2012,
        //   selected: false,
        // },
        // {
        //   key: 5,
        //   title: "QuickPickMovies",
        //   description:
        //     "A web platform designed to help users with movies recommendations and information",
        //   tools:
        //     "Firebase gathering data from an external API (RapidAPI), front using NuxtJS",
        //   link: "https://github.com/MassineM/QuickPickMovies",
        //   year: 2022,
        //   selected: false,
        // },
        // {
        //   key: 1,
        //   title: "This WEB portfolio",
        //   description:
        //     "Personnal project made from scratch, firstly in the purpose of publishing an accessible Curriculum Vitae, before the ambition of completing a rich portfolio took over",
        //   tools:
        //     "Nuxt.JS based, icons using Illustrator, SASS for animations, mainly structured by Vue.JS and JavaScript",
        //   link: "https://github.com/MassineM/portfolio",
        //   year: 2022,
        //   selected: true,
        // },
        // {
        //   key: 5,
        //   title: "Connect 4",
        //   description: "Console based player versus player game",
        //   tools: "Basic Java console application",
        //   link: "https://github.com/MassineM/Connect4",
        //   year: 2021,
        //   selected: false,
        // },
        // {
        //   key: 6,
        //   title: "Truck Platooning",
        //   description:
        //     "Supervised personal initiative work as a part of the preparatory classes for engineering schools contests",
        //   tools:
        //     "Research and study of functionnal & technical aspects of platooning technologies on heavy vehicles",
        //   link: "https://drive.google.com/file/d/1JgaUU-GB__JA06fEcK7taSBWlnE0Fk1W/view?usp=sharing",
        //   year: 2019,
        //   selected: false,
        // // },
        // {
        //   key: 7,
        //   title: "Motus",
        //   description:
        //     "Based on the famous Lingo television game, this is a French version named Motus based console game",
        //   tools: "Fully developped by C language",
        //   link: "https://github.com/MassineM/motus",
        //   year: 2019,
        //   selected: false,
        // },
      ],
    };
  },
  mounted: function () {
    this.selectTab(this.projects[0]);
  },
  methods: {
    selectTab(tab) {
      if (this.selectedTab.key != tab.key) {
        this.show = false;
        setTimeout(() => {
          this.show = true;
        }, 500);
        this.selectedTab = tab;
        for (const each of this.projects) {
          each.selected = false;
        }
        tab.selected = true;
      }
    },
  },
};
</script>
<style lang="scss" scoped></style>
