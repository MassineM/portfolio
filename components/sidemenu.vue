<template>
  <div class="sidemenuContainer">
    <nav>
      <ul>
        <Transition name="fade">
          <span
            class="text"
            v-if="get_hovered_text() != null"
            :style="{ top: hovered_top }"
          >
            {{ get_hovered_text() }}</span
          >
        </Transition>
        <div
          id="shadowCurr"
          :style="{ top: selected_top }"
          class="currshadow"
        ></div>
        <li
          v-for="item of nav"
          v-html="item.svg"
          :id="`item_${item.key}`"
          :key="item.key"
          @click="selectCurrent(item)"
          class="icon"
          :class="{ active: item.selected }"
          @mouseenter="hoverMyItem(item)"
          @mouseleave="leaveMyItem()"
        ></li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  props: [],
  mounted: function () {
    window.addEventListener("mousemove", this.mouseIsMoving);
    document.addEventListener("mousewheel", this.onScroll.bind(this), {
      passive: false,
    });
    document.addEventListener("keydown", this.keyScroll);
    this.onBanner = false;
    this.onTab = false;
    this.selectCurrent(this.nav[0]);
    this.$root.$on("sidemenu", () => {
      this.selectCurrent(this.nav[1]);
    });
  },
  data: function () {
    return {
      iconsPath: "~/assets/icons/",
      pointer: 0,
      isScrolling: 0,
      // pointerIcon:
      //   '<svg style="enable-background:new 0 0 100 100" viewBox="0 0 100 100" xml:space="preserve" xmlns="http://www.w3.org/2000/svg"><path d="M41.762 27.26v8.294c0 .571.305 1.1.8 1.385l20.212 11.669c1.066.616 1.066 2.155 0 2.771L42.562 63.048c-.495.286-.8.814-.8 1.385v8.294c0 1.231 1.333 2.001 2.399 1.385l39.375-22.733c1.066-.616 1.066-2.155 0-2.771L44.161 25.875c-1.066-.616-2.399.154-2.399 1.385z"/><path d="M83.537 48.608 44.161 25.875c-.193-.112-.395-.164-.597-.19l37.972 21.923c1.066.616 1.066 2.155 0 2.771L42.161 73.112c-.1.058-.205.092-.308.126.308.914 1.401 1.398 2.308.874l39.375-22.733c1.067-.616 1.067-2.155.001-2.771z"/><path d="M41.762 27.26v8.294c0 .571.305 1.1.8 1.385l20.212 11.669c1.066.616 1.066 2.155 0 2.771L42.562 63.048c-.495.286-.8.814-.8 1.385v8.294c0 1.231 1.333 2.001 2.399 1.385l39.375-22.733c1.066-.616 1.066-2.155 0-2.771L44.161 25.875c-1.066-.616-2.399.154-2.399 1.385z" style="fill:none;stroke:#000;stroke-miterlimit:10"/><path d="M14.664 27.273v8.294c0 .571.305 1.1.8 1.385l20.212 11.669c1.066.616 1.066 2.155 0 2.771L15.464 63.061c-.495.286-.8.814-.8 1.385v8.294c0 1.231 1.333 2.001 2.399 1.385l39.375-22.733c1.066-.616 1.066-2.155 0-2.771L17.063 25.888c-1.066-.616-2.399.154-2.399 1.385z"/><path d="M56.438 48.621 17.063 25.888c-.193-.112-.395-.164-.597-.19l37.972 21.923c1.066.616 1.066 2.155 0 2.771L15.063 73.125c-.1.058-.205.092-.308.126.308.914 1.401 1.398 2.308.874l39.375-22.733c1.067-.616 1.067-2.155 0-2.771z"/><path d="M14.664 27.273v8.294c0 .571.305 1.1.8 1.385l20.212 11.669c1.066.616 1.066 2.155 0 2.771L15.464 63.061c-.495.286-.8.814-.8 1.385v8.294c0 1.231 1.333 2.001 2.399 1.385l39.375-22.733c1.066-.616 1.066-2.155 0-2.771L17.063 25.888c-1.066-.616-2.399.154-2.399 1.385z" style="fill:none;stroke:#000;stroke-miterlimit:10"/></svg>',
      nav: [
        {
          key: 1,
          text: "Index",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" data-name="Layer 2" viewBox="0 0 49.74 49.74"><g data-name="Layer 1"><path d="M24.87 0C11.13 0 0 11.13 0 24.87s11.13 24.87 24.87 24.87 24.87-11.13 24.87-24.87S38.61 0 24.87 0Zm15.88 39.21c-7.89 8.77-21.41 9.49-30.18 1.59A21.366 21.366 0 0 1 3.7 21.94c.56-4.11 2.31-8.1 5.29-11.41 7.89-8.77 21.41-9.49 30.18-1.59a21.366 21.366 0 0 1 6.87 18.86c-.56 4.11-2.31 8.1-5.29 11.41Z"/><path d="M29.59 34.3V20.04c0-.64-.52-1.16-1.16-1.16H18.9c-.64 0-1.16.52-1.16 1.16v4.8c0 .64.52 1.16 1.16 1.17.63 0 1.15.5 1.16 1.13v7.16c0 .64-.52 1.16-1.16 1.16-.64 0-1.16.52-1.16 1.16v5.1c0 .64.52 1.16 1.16 1.16h11.94c.64 0 1.16-.52 1.16-1.16v-5.05c0-.64-.52-1.16-1.16-1.16h-.09c-.64 0-1.16-.52-1.16-1.16v-.05Z"/><circle cx="23.95" cy="11.55" r="4.69"/></g></svg>',
          selected: true,
          hovered: false,
        },
        {
          key: 2,
          text: "About",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 49.74 49.74"><defs/><g id="Calque_2" data-name="Calque 2"><g id="Calque_6" data-name="Calque 6"><circle class="cls-1" cx="24.87" cy="18.98" r="8.76"/><path class="cls-1" d="m42.93 42 .21-.23c.29-.31.58-.63.85-1 .29-.35.57-.71.84-1.07l.11-.15c.22-.31.44-.61.65-.93l.2-.32c.17-.26.34-.53.5-.8s.14-.26.22-.38l.43-.8c.06-.13.13-.26.2-.39s.27-.57.4-.86c0-.12.11-.23.16-.35.17-.38.32-.77.46-1.16a.3.3 0 0 0 0-.08c.15-.42.29-.85.43-1.28 0-.12.06-.24.1-.36.09-.31.18-.62.25-.94 0-.16.08-.32.11-.47s.13-.57.18-.86.07-.34.1-.51.09-.58.12-.86.05-.35.07-.52.06-.62.08-.94v-3.12c-.05-.85-.13-1.69-.26-2.51a24.87 24.87 0 0 0-49.16 0c-.02.79-.1 1.63-.18 2.48v3.1c0 .31 0 .62.08.92s.05.35.07.52l.19.87c0 .18.06.35.1.53s.1.54.16.81l.12.5c.07.28.14.56.22.83s.08.31.13.46c.09.31.2.62.3.92 0 .11.07.22.11.33.15.42.31.83.49 1.24v.06c.16.38.33.76.51 1.13.06.11.12.22.17.33.14.28.29.56.44.83l.22.38c.15.25.29.5.45.75l.24.38.5.73.25.35c.18.25.37.49.56.74l.23.28c.24.3.49.6.75.89l.09.1c.3.33.61.65.92 1 .3.29.6.58.92.86l.24.21.75.63.11.1.38.29.1.07.18.14.09.07h.05l.39.27.09.06c.49.34 1 .67 1.51 1h.13l.38.21.1.06h.1l.18.1h.08l.11.06.37.19h.19c.31.16.63.31 1 .45l.19.09h.1l.15.06.16.06.17.08.33.12.2.08h.31l.22.07.31.11.22.07h.14l.27.09h.14l.27.08.27.08.28.07H18.71l.29.07.27.06.3.07H20l.33.06h.24l.41.07h.12l.56.08H28.07l.57-.08h.12l.41-.07h.24l.33-.06h.22l.3-.07.27-.06.28-.07.19.6h.12l.27-.07.28-.08.26-.07.14-.05.28-.09h.14l.22-.07.31-.11.21-.07h.32l.2-.08.33-.12.17-.07.16-.07.15-.06h.09l.19-.09c.33-.14.64-.29 1-.45h.18l.38-.19.1-.06h.08l.19-.1h.1l.1-.06.37-.21h.13q1-.59 1.92-1.26l.08-.05.09-.07.18-.13.09-.08.17-.14c.27-.21.54-.42.79-.64l.29-.25.71-.65.28-.26ZM24.87 29.86a15.55 15.55 0 0 0-14.65 10.52 21.37 21.37 0 1 1 29.3 0 15.56 15.56 0 0 0-14.65-10.52Z"/></g></g></svg>',
          selected: false,
          hovered: false,
        },
        {
          key: 3,
          text: "Projects",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 49.74 49.74"><defs/><g id="Calque_2" data-name="Calque 2"><g id="Calque_6" data-name="Calque 6"><path class="cls-1" d="M31.93 18.05 20.7 17a.73.73 0 0 0-.13 1.46l11.23 1h.07a.72.72 0 0 0 .72-.66.74.74 0 0 0-.66-.75ZM31.67 21.24l-11.24-1a.73.73 0 1 0-.13 1.45l11.23 1h.07a.73.73 0 0 0 .07-1.45Z"/><path class="cls-1" d="M24.87 0a24.87 24.87 0 1 0 24.87 24.87A24.86 24.86 0 0 0 24.87 0Zm9 16.3 2.29.2-.65 8.21h-6.84a1.23 1.23 0 0 0-1.07.62l-1.9 3.33h-9.46l-.14-.28 1.45-16.14 16 1.48-.17 2a.55.55 0 0 0 .53.58ZM14.61 28.66h-.35A1.31 1.31 0 0 0 13 30v10.9a1 1 0 0 1-1-1V25.83h3l-.26 2.83ZM39.29 40.6V25.93a1.22 1.22 0 0 0-1.22-1.22H37l.65-8.24.09-1.15v-.27l-.19-.19-2.27-2.32-.15-.15h-.22l-1.26-.12-16-1.49h-.14a1.48 1.48 0 0 0-1.47 1.35L15 24.38h-3.29a1.28 1.28 0 0 0-1.28 1.28v14.23a2.48 2.48 0 0 0 .15.82 21.37 21.37 0 1 1 28.71-.11Z"/></g></g></svg>',
          selected: false,
          hovered: false,
        },
        {
          key: 4,
          text: "Skills",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 49.74 49.74"><g data-name="Calque 2"><g data-name="Calque 6"><path class="cls-1" d="M24.87 0a24.87 24.87 0 1 0 24.87 24.87A24.86 24.86 0 0 0 24.87 0Zm0 46.24a21.37 21.37 0 1 1 21.37-21.37 21.4 21.4 0 0 1-21.37 21.37Z"/><path class="cls-1" d="M37.54 12.55H21.22a.81.81 0 0 0 0 1.62h16.32a.81.81 0 0 0 0-1.62ZM21.22 17.5h8.16a.81.81 0 1 0 0-1.61h-8.16a.81.81 0 0 0 0 1.61Zm16.32 4.89H21.22a.81.81 0 0 0 0 1.62h16.32a.81.81 0 0 0 0-1.62Zm-16.32 4.95h8.16a.81.81 0 1 0 0-1.61h-8.16a.81.81 0 0 0 0 1.61Zm16.32 4.89H21.22a.81.81 0 0 0 0 1.62h16.32a.81.81 0 0 0 0-1.62Zm-8.16 3.34h-8.16a.81.81 0 0 0 0 1.61h8.16a.81.81 0 1 0 0-1.61ZM17.83 17.39a1.38 1.38 0 0 0 .76-1.24v-2.24a1.38 1.38 0 0 0-.76-1.24l-2.47-1.23a1.4 1.4 0 0 0-1.23 0l-2.47 1.23a1.37 1.37 0 0 0-.77 1.24v2.24a1.37 1.37 0 0 0 .77 1.24l1.82.9v3.31l-1.82.91a1.37 1.37 0 0 0-.77 1.24V26a1.37 1.37 0 0 0 .77 1.24l1.82.9v3.31l-1.82.91a1.37 1.37 0 0 0-.77 1.24v2.24a1.37 1.37 0 0 0 .77 1.24l2.47 1.23a1.43 1.43 0 0 0 .61.14 1.51 1.51 0 0 0 .62-.14l2.47-1.23a1.38 1.38 0 0 0 .76-1.24v-2.25a1.38 1.38 0 0 0-.76-1.24l-1.74-.86v-3.4l1.74-.86a1.38 1.38 0 0 0 .76-1.23v-2.25a1.38 1.38 0 0 0-.76-1.24l-1.74-.86v-3.4ZM14.74 35.5a.79.79 0 0 1 0-1.58.79.79 0 0 1 0 1.58Zm0-9.84a.79.79 0 0 1 0-1.58.79.79 0 1 1 0 1.58Zm0-9.84a.79.79 0 0 1 0-1.58.79.79 0 0 1 0 1.58Z"/></g></g></svg>',
          selected: false,
          hovered: false,
        },
        {
          key: 5,
          text: "More",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" xml:space="preserve" style="enable-background:new 0 0 49.7 49.7" viewBox="0 0 49.7 49.7"><path d="M24.9 0C11.1 0 0 11.1 0 24.9s11.1 24.9 24.9 24.9 24.9-11.1 24.9-24.9C49.7 11.1 38.6 0 24.9 0zm0 46.2c-11.8 0-21.4-9.6-21.4-21.4S13.1 3.5 24.9 3.5s21.4 9.6 21.4 21.4c-.1 11.8-9.6 21.3-21.4 21.3z"/><path d="M25.1 39.8c-3 0-5.5-.5-7.5-1.5s-3.5-2.4-4.6-4.1c-1-1.8-1.7-3.8-1.9-6.1 0-.3 0-.8-.1-1.4v-3.6c0-.6 0-1 .1-1.3.1-1.6.5-3 1.2-4.5.6-1.4 1.5-2.7 2.6-3.8 1.1-1.1 2.5-2 4.1-2.6 1.6-.6 3.5-.9 5.6-.9 2.6 0 4.7.3 6.5.9 1.8.6 3.2 1.4 4.3 2.5 1.1 1.1 1.9 2.3 2.5 3.8.5 1.4.9 3 1 4.7 0 .5.1 1.1.1 1.7v1.7c0 .5 0 1-.1 1.3-.1 1.2-.4 2.3-.9 3.1-.5.8-1.2 1.5-2 1.9-1 .2-1.9.4-2.8.4-.8 0-1.5-.1-2.1-.3-.6-.2-1.1-.5-1.5-.8-.4-.3-.7-.5-.9-.8-.2.3-.4.6-.8 1-.3.4-.8.7-1.4.9-.6.2-1.5.4-2.6.4-1.8 0-3.3-.7-4.3-2S18 27.2 18 24.9s.5-4.2 1.5-5.5c1-1.4 2.4-2 4.3-2 1 0 1.8.2 2.3.5.6.3 1 .7 1.4 1.2v-.5c0-.3.1-.5.3-.7.2-.2.4-.3.7-.3h1.9c.3 0 .5.1.7.3.2.2.3.4.3.7V26c0 .8.2 1.4.5 1.8.3.4.8.6 1.4.6.5 0 .9-.1 1.2-.4.3-.3.5-.6.6-1 .1-.4.2-.7.2-1.1V24c0-.7 0-1.4-.1-2.2-.1-1.9-.5-3.4-1.2-4.7-.7-1.2-1.8-2.2-3.3-2.8-1.5-.6-3.5-.9-6-.9-2.1 0-3.8.4-5.2 1.1s-2.4 1.7-3.2 2.9c-.8 1.3-1.2 2.7-1.4 4.4 0 .4-.1 1-.1 1.8v2.3c0 .8 0 1.4.1 1.9.3 2.6 1.3 4.7 2.9 6.1s4.1 2.2 7.4 2.2c1.5 0 2.8-.1 3.7-.3.9-.2 1.7-.4 2.2-.7s1.1-.6 1.5-.9c.2-.1.4-.3.5-.4.2-.1.4-.1.6-.1h2.6c.2 0 .5.1.6.3s.3.4.2.7c0 .1 0 .2-.1.3 0 .1-.1.2-.2.2-.7.8-1.6 1.5-2.6 2.2-1 .7-2.3 1.3-3.8 1.7-1.4.4-3.2.7-5.3.7zm-.5-11c1 0 1.7-.3 2.2-1 .5-.6.7-1.6.7-3s-.2-2.4-.7-3c-.5-.7-1.2-1-2.2-1-.9 0-1.7.3-2.1 1-.5.7-.7 1.7-.7 3 0 .8.1 1.6.3 2.1.2.6.5 1 1 1.4s.8.5 1.5.5z"/></svg>',
          selected: false,
          hovered: false,
        },
      ],
      selected_top: 0,
      hovered_top: 0,
      currTab: "1",
      // cursor_top: 0,
      // shadow_opacity: 0,
    };
  },
  methods: {
    // mouseIsMoving(e) {
    //   let vw = Math.max(
    //     document.documentElement.clientWidth || 0,
    //     window.innerWidth || 0
    //   );
    //   let vh = Math.max(
    //     document.documentElement.clientHeight || 0,
    //     window.innerHeight || 0
    //   );
    //   this.vw = Math.max(
    //     document.documentElement.clientWidth || 0,
    //     window.innerWidth || 0
    //   );
    //   this.vh = Math.max(
    //     document.documentElement.clientHeight || 0,
    //     window.innerHeight || 0
    //   );
    //   let xPercent = e.pageX / vw;
    //   let yPercent = e.pageY / vw;
    //   // this.xPercent = xPercent;

    // this.cursor_top = (e.pageY % vh) + "px";
    //   if (this.get_hovered_text() == null)
    //     this.shadow_opacity = (0.25 - xPercent) * 3;
    //   else this.shadow_opacity = 1;
    // },
    selectCurrent(item) {
      let i = 0;
      for (const li of this.nav)
        if (li.key == item.key) {
          li.selected = true;
          this.selected_top =
            document.getElementById("item_" + li.key).offsetTop + "px";
          this.pointer = i;
          document.getElementById(this.nav[i].text).scrollIntoView({
            behavior: "smooth",
            block: "start",
            inline: "nearest",
          });
          i++;
        } else {
          li.selected = false;
          i++;
        }
    },

    get_hovered_text() {
      for (const item of this.nav) if (item.hovered) return item.text; //  Fills span with the matching tab title
    },

    hoverMyItem(item) {
      let vh = Math.max(
        document.documentElement.clientHeight || 0,
        window.innerHeight || 0
      );
      for (const li of this.nav) {
        if (li.key == item.key) {
          li.hovered = true;
          this.hovered_top =
            document.getElementById("item_" + li.key).offsetTop +
            (1.3 * vh) / 100 +
            "px";
        } else li.hovered = false;
      }
    },

    leaveMyItem() {
      for (const item of this.nav) item.hovered = false;
    },

    onScroll(e) {
      e.preventDefault();
      if (this.isScrolling) return;
      this.isScrolling = 1;
      setTimeout(() => {
        this.isScrolling = 0;
      }, 600);
      console.log(e);
      if (e.deltaY > 6) {
        this.pointer = (this.pointer + 1) % this.nav.length;
        this.selectCurrent(this.nav[this.pointer]);
      } else if (e.deltaY < -6) {
        this.pointer = (this.pointer - 1) % this.nav.length;
        if (this.pointer < 0) this.pointer += this.nav.length;
        this.selectCurrent(this.nav[this.pointer]);
      }
      console.log(this.pointer);
    },

    keyScroll(e) {
      if ([8, 38, 33, 37, 36].includes(e.keyCode)) {
        e.preventDefault();
        this.pointer = (this.pointer - 1 + this.nav.length) % this.nav.length;
        this.selectCurrent(this.nav[this.pointer]);
      } else if ([9, 32, 40, 34, 39, 35].includes(e.keyCode)) {
        e.preventDefault();
        this.pointer = (this.pointer + 1) % this.nav.length;
        this.selectCurrent(this.nav[this.pointer]);
      }
    },
  },
};
</script>
