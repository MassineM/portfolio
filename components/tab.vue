<template>
  <div></div>
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
  },
  methods: {
  },
};
</script>

<style></style>
