<template>
  <div id="app">
    <Navbar />
    <Home />
    <Descriptions />
    <BlockBase />
    <BlockHBG />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Home from "./components/Home.vue";
import Descriptions from "./components/Descriptions.vue";
import BlockBase from "./components/BlockBase.vue";
import BlockHBG from "./components/BlockHBG.vue";

export default {
  name: 'App',
  components: {
    Navbar, Home, Descriptions, BlockBase, BlockHBG
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
