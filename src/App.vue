<template>
  <the-header></the-header>
  <home-page></home-page>
  <bio-page></bio-page>
  <timeline-page></timeline-page>
  <projects-page></projects-page>
</template>

<script setup>
import { defineComponent } from "vue";
import TheHeader from "./components/TheHeader.vue";
import HomePage from "./components/pages/HomePage.vue";
import BioPage from "./components/pages/BioPage.vue";
import TimelinePage from "./components/pages/TimelinePage.vue";

import ProjectsPage from "./components/pages/ProjectsPage.vue";
defineComponent("home-page");
defineComponent("the-header");
defineComponent("bio-page");
defineComponent("timeline-page");
defineComponent("projects-page");
</script>

<style lang="scss">
@mixin global-format {
  padding: 0;
  margin: 0;
  box-sizing: inherit;
}

* {
  @include global-format;

  &::after &::before {
    @include global-format;
  }
}

html {
  font-size: 62.5%;

  @media screen and (max-width: 500px) {
    font-size: 50%;
  }
}
body {
  box-sizing: border-box;
}

#app {
  font-family: "Helvetica Neue", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  background: rgb(16, 16, 57);
  height: 100dvh;
  overflow-x: hidden;
}
</style>
