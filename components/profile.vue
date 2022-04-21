<template>
  <div id="profile">
    <div class="mainArticle">
      <h1 class="title">Who am I?</h1>
      <div class="profiletop">
        <div>
          <p class="text">"Ambition is key to foul the odds"</p>
          <p class="text">
            ~ Massine Mountasser, 22 years old, computer science engineering
            student
          </p>
          <p class="text">
            "I believe an internship would help me discover my full potential in
            real situations and that's fine by me, for how big my love for
            challenge is..."
          </p>
          <a
            :href="`https://drive.google.com/drive/folders/1w-tLF6T2wAaspsS4VIjSmT4pZ61an9rS?usp=sharing`"
            target="_blank"
            class="hiveElmnt"
          >
            <span v-html="link1"> </span>Link to some of my certifications...</a
          >
        </div>
        <img src="~/assets/ME2.png" class="pid" style="filter: saturate(0)" />
      </div>
      <p class="text" STYLE="padding:0 0 0 5vw;">
        ~ Before highschool (till 2016) - Born in Agadir on may 13th of 1999, I
        have always managed to get myself amazed by any technology I came
        across. Playing with electronics as a child, coding mini games in early
        teenage years, enrolling to mechanic studies in highschool...
      </p>
      <p class="text" STYLE="padding:0 5vw 0 0;">
        ~ Baccalaureate (2017) - When I got my baccalaureate in mechanical techs
        and sciences, it seemed like I was destined to take a step back and
        study many more technical, scientific and litterary domains.
      </p>
      <p class="text" STYLE="padding:0 0 0 5vw;">
        ~ Preparatory classes (2017-2019) - I spent the next two years in
        preparatory classes for engineering schools - industrial technologies
        and sciences branch (CPGE TSI). Once done with all of the orientation
        and school acceptance contests, I was more than happy to join the
        Littoral Côte d'Opale's engineering school of information technologies,
        with which I still am today.
      </p>
      <p class="text" STYLE="padding:0 5vw 0 0;">
        ~ Engineering school (since 2019) - This leads us to the main purpose of
        this website I made while personally practicing web development: I'm
        still looking for an internship with some company that wants some
        profile in computer science near mine, and with whom I'd learn about
        real workspaces organisation and methods.
      </p>
    </div>
  </div>
</template>

<script>
//document.addEventListener('mousemove',function(e){mypageY=e.pageY;});
export default {
  data: function () {
    return {
      link1:
        '<svg xmlns="http://www.w3.org/2000/svg" id="OBJECT" viewBox="0 0 512 512"><defs><style>.cls-1{fill:#bddbff}.cls-2{fill:#3d9ae2}</style></defs><rect width="497" height="350" x="7.5" y="81" class="cls-1" rx="20" ry="20"/><path d="M484.5 438.5h-457A27.54 27.54 0 0 1 0 411V101a27.54 27.54 0 0 1 27.5-27.5h457A27.54 27.54 0 0 1 512 101v310a27.54 27.54 0 0 1-27.5 27.5Zm-457-350A12.52 12.52 0 0 0 15 101v310a12.52 12.52 0 0 0 12.5 12.5h457A12.52 12.52 0 0 0 497 411V101a12.52 12.52 0 0 0-12.5-12.5Z" class="cls-2"/><path fill="#fff" d="M416 116H96a50 50 0 0 1-50 50v180a50 50 0 0 1 50 50h320a50 50 0 0 1 50-50V166a50 50 0 0 1-50-50Z"/><path d="M416 403.5H96a7.5 7.5 0 0 1-7.5-7.5A42.55 42.55 0 0 0 46 353.5a7.5 7.5 0 0 1-7.5-7.5V166a7.5 7.5 0 0 1 7.5-7.5A42.55 42.55 0 0 0 88.5 116a7.5 7.5 0 0 1 7.5-7.5h320a7.5 7.5 0 0 1 7.5 7.5 42.55 42.55 0 0 0 42.5 42.5 7.5 7.5 0 0 1 7.5 7.5v180a7.5 7.5 0 0 1-7.5 7.5 42.55 42.55 0 0 0-42.5 42.5 7.5 7.5 0 0 1-7.5 7.5Zm-313-15h306a57.61 57.61 0 0 1 49.5-49.5V173a57.61 57.61 0 0 1-49.5-49.5H103A57.61 57.61 0 0 1 53.5 173v166a57.61 57.61 0 0 1 49.5 49.5Z" class="cls-2"/><path d="m286 366-30-15-30 15V266h60v100z" class="cls-1"/><path d="M286 373.5a7.43 7.43 0 0 1-3.35-.79L256 359.39l-26.65 13.32A7.5 7.5 0 0 1 218.5 366V266a7.5 7.5 0 0 1 7.5-7.5h60a7.5 7.5 0 0 1 7.5 7.5v100a7.5 7.5 0 0 1-7.5 7.5Zm-30-30a7.43 7.43 0 0 1 3.35.79l19.15 9.57V273.5h-45v80.36l19.15-9.57a7.43 7.43 0 0 1 3.35-.79Z" class="cls-2"/><circle cx="256" cy="266" r="50" class="cls-1"/><path d="M256 323.5a57.5 57.5 0 1 1 57.5-57.5 57.56 57.56 0 0 1-57.5 57.5Zm0-100a42.5 42.5 0 1 0 42.5 42.5 42.55 42.55 0 0 0-42.5-42.5Z" class="cls-2"/><path d="M371 181H141a15 15 0 0 1 0-30h230a15 15 0 0 1 0 30Z" class="cls-1"/><path d="M371 188.5H141a22.5 22.5 0 0 1 0-45h230a22.5 22.5 0 0 1 0 45Zm-230-30a7.5 7.5 0 0 0 0 15h230a7.5 7.5 0 0 0 0-15Z" class="cls-2"/></svg>',
    };
  },
  methods: {},
};
</script>
<style lang="scss" scoped></style>
