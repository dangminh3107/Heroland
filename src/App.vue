<template>
  <div id="app">
    <Navbar />
    <Home :pos="pos"/>
    <Descriptions :pos="pos"/>
    <BlockBase :pos="pos"/>
    <BlockHBG :pos="pos"/>
    <Roadmap :pos="pos"/>
    <BlockPartner :pos="pos"/>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Home from "./components/Home.vue";
import Descriptions from "./components/Descriptions.vue";
import BlockBase from "./components/BlockBase.vue";
import BlockHBG from "./components/BlockHBG.vue";
import Roadmap from "./components/Roadmap.vue";
import BlockPartner from "./components/BlockPartner.vue";

export default {
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll);
  },
  name: 'App',
  components: {
    Navbar, Home, Descriptions, BlockBase, BlockHBG, Roadmap, BlockPartner,
  },
  data() {
    return {
      pos: 0,
    }
  },
  methods: {
    handleScroll() {
      this.pos = window.scrollY;
    }
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap");
@import "./assets/css/base.css";
* {
  margin: 0;
  padding: 0;
  box-sizing: inherit;
}

html {
  box-sizing: border-box;
  font-family: "Space Mono", monospace;
}

::-webkit-scrollbar {
  width: 12px;
}

::-webkit-scrollbar-thumb {
  background: var(--main-color);
}

::-webkit-scrollbar-track {
  background: var(--black-color);
}
</style>
