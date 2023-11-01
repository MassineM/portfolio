<template>
  <div id="About" class="mainArticle">
    <h1 class="title">About me</h1>
    <div class="profiletop">
      <div class="timeline">
        <a
          :href="`https://drive.google.com/drive/folders/1w-tLF6T2wAaspsS4VIjSmT4pZ61an9rS?usp=sharing`"
          target="_blank"
          class="certifications"
          style="width: fit-content; margin-left: auto; margin-right: auto"
        >
          <span v-html="link1"> </span>Click here to see my certifications</a
        >
        <p
          class="profileText"
          STYLE="padding:3vh 0 0 3vw;font-style: italic;font-weight: 900;"
        >
          ~ Engineering school (2019-2023)
        </p>
        <p class="profileText" STYLE="padding:0 4vw 0 0; text-align: left">
          Having completed my computer science engineering course at the
          Littoral Côte d'Opale's engineering school of information technologies
          (EILco - Calais, France), I am now looking for a job as an IT
          engineer, preferably in the web development field.
        </p>

        <p
          class="profileText"
          STYLE="padding:3vh 3vw 0 0;font-style: italic;font-weight: 900; text-align: right"
        >
          ~ Preparatory classes (2017-2019)
        </p>
        <p class="profileText" STYLE="padding:0 0 0 4vw; text-align: right">
          Two years of preparatory classes for engineering schools - industrial
          technologies and sciences branch (CPGE TSI Reda Slaoui - Agadir,
          Morocco), followed by school hiring contests. I was more than happy to
          go in for an IT school by the end.
        </p>
        <p
          class="profileText"
          STYLE="padding:3vh 0 0 3vw;font-style: italic;font-weight: 900; text-align: left"
        >
          ~ Baccalaureate (2017)
        </p>
        <p class="profileText" STYLE="padding:0 4vw 0 0; text-align: left">
          Got my baccalaureate in mechanics, techs and sciences highschool
          Youssef Ben Tachfine in Agadir, Morocco. Good enough grades for a
          national competition in engineering sciences, and made it to
          preparatory classes.
        </p>
        <p
          class="profileText"
          STYLE="padding:3vh 3vw 0 0;font-style: italic;font-weight: 900; text-align: right"
        >
          ~ Before highschool (till 2016)
        </p>
        <p class="profileText" STYLE="padding:0 0 0 4vw; text-align: right">
          Born in Agadir on may 13th of 1999, I was good at maths and have
          always managed to get myself amazed by any technology I came across. I
          loved playing with electronics as a child, and coding mini games since
          early teenage years.
        </p>
      </div>
      <p class="pid">
        Commitment determination <br />
        initiative motivation <br />
        vigour dynamism <br />
        energy vitality <br />
        development evolution <br />
        progress growth <br />
        audacity courage <br />
        ambition enthusiasm <br />
        curiosity perception <br />
        reasoning logic <br />
        inspiration creativity <br />
        originality art <br />
        patience altruism <br />
        compassion goodwill
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
