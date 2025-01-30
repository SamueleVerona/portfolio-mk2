<template>
  <section class="section-bio">
    <h2 class="bio__title">About me</h2>
    <div class="bio__img"></div>
    <h3 class="bio__subtitle">Front End Web Developer</h3>
    <p class="bio__text">
      I'm 26 years old and since May of 2024 i have been studying web
      development. <br />
      Here you can find information about my journey and have a look at my most
      recent projects and codebase. Check out the projects' section to see more!
    </p>

    <a class="bio__link">go to projects</a>
  </section>
</template>

<style lang="scss" scoped>
.section-bio {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  height: 100dvh;
  padding: 1rem;
  text-align: center;

  .bio__title {
    font-size: 5rem;
  }

  .bio__img {
    position: relative;
    width: 8rem;
    height: 8rem;

    aspect-ratio: 1;
    background: url(/src/assets/img/layers.png);
    background-size: cover;
    background-position: center;
    border-radius: 100%;

    &::before,
    &::after {
      position: absolute;
      top: -6%;
      left: -6%;
      width: 8rem;
      height: 8rem;
      padding: 0.5rem;
      background: rgb(255, 255, 255);

      aspect-ratio: 1;
      border-radius: 100%;
      border: none;
      content: "";
    }
    &::after {
      z-index: -2;
    }

    &::before {
      padding: 1rem;
      top: -12.5%;
      left: -12.5%;
      border: none;

      z-index: -1;
      transform: rotateZ(0deg);

      background: linear-gradient(
        to bottom,
        rgb(255, 255, 255) 30%,
        rgb(0, 183, 255) 31%,
        rgb(89, 0, 255) 100%
      );
      background-size: 200% 200%;
      animation: rotation 3s linear infinite forwards;

      @keyframes rotation {
        0% {
          transform: rotateZ(0deg);
        }
        100% {
          transform: rotateZ(360deg);
        }
      }
    }
  }
  .bio__subtitle {
    font-size: 3rem;
  }

  .bio__text {
    display: -webkit-box;
    padding: 0rem 2rem;
    font-size: 2rem;
    font-weight: 600;
    max-width: 85%;

    line-clamp: 5;
    text-align: center;
    white-space: pre-wrap;
  }

  .bio__link {
    font-size: 2rem;
    font-weight: 600;
  }
}
</style>
