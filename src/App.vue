<template>
  <the-header></the-header>

  <home-page id="home"></home-page>
  <bio-page id="bio" class="page"></bio-page>
  <timeline-page id="time"></timeline-page>
  <projects-page id="projects"></projects-page>
  <contacts-page id="links"></contacts-page>
</template>

<script setup>
import { defineComponent } from "vue";
import TheHeader from "./components/TheHeader.vue";
import HomePage from "./components/pages/HomePage.vue";
import BioPage from "./components/pages/BioPage.vue";
import TimelinePage from "./components/pages/TimelinePage.vue";
import ProjectsPage from "./components/pages/ProjectsPage.vue";
import ContactsPage from "./components/pages/ContactsPage.vue";

defineComponent("home-page");
defineComponent("the-header");
defineComponent("bio-page");
defineComponent("timeline-page");
defineComponent("projects-page");
defineComponent("contacts-page");
</script>

<style lang="scss">
@import "@/assets/styles/fonts.css";

:root {
  --theme-primary: rgb(68, 192, 249);
  --transition-default: all 0.3s ease;
}

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

  @media screen and (max-width: 400px) {
    font-size: 40%;
  }

  @media screen and (max-width: 748px) and (orientation: landscape) {
    font-size: 50%;
  }
}
body {
  box-sizing: border-box;
  margin: 0;
  overflow-x: hidden;

  &::-webkit-scrollbar-thumb {
    padding: 0.2rem;
    background-color: rgb(34, 77, 133);
    border: 2px solid transparent;
    border-radius: 8px;
    background-clip: padding-box;
  }
  &::-webkit-scrollbar {
    border-radius: 8px;
    background: rgb(255, 255, 255);
    width: 10px;
  }
}

#app {
  font-family: "Helvetica Neue", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, Arial, sans-serif;
  color: #ffffff;
  background: linear-gradient(to right, rgb(16, 16, 57), rgb(34, 77, 133) 60%);
}
</style>
