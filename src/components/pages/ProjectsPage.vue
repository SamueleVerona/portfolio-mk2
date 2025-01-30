<template>
  <section class="section-projects">
    <a class="project project--1"></a>
    <a class="project project--2"></a>
    <a class="project project--3"></a>
    <a class="project project--4"></a>
    <div class="pivot-img"></div>
  </section>
</template>

<style lang="scss" scoped>
.section-projects {
  height: 100dvh;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  //   border: solid;

  .pivot-img {
    position: relative;

    width: 10rem;
    aspect-ratio: 1;
    background: url(/src/assets/img/layers.png);
    background-size: contain;
    // margin: 50% auto;
    // transform: translateY(-50%);
    // border: solid;
  }
  .project {
    position: absolute;
    width: 6rem;
    aspect-ratio: 1;
    // top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);

    font-size: 3rem;
    display: flex;
    flex-direction: column;
    background: url(/src/assets/img/layers.png);
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
    // border: solid;
    // border-radius: 100%;

    cursor: pointer;

    offset-path: path("M 300 0 A 300 300 0 1 0 -300 0 A 300 300 0 1 0 300 0");
    offset-anchor: 50%;

    animation: firefly 15s linear infinite;
    transform-style: preserve-3d;

    $distance-offset: 0%;

    &.project--1 {
      animation-delay: 0s;
      background: url(/src/assets/img/favicon.ico);
      background-size: contain;
    }
    &.project--2 {
      animation-delay: -3.75s;
    }
    &.project--3 {
      animation-delay: -7.5s;
    }
    &.project--4 {
      animation-delay: -11.25s;
    }

    @keyframes firefly {
      0% {
        offset-distance: 0%;
        transform: rotate(-360deg);
      }

      100% {
        offset-distance: 100%;
        transform: rotate(360deg);
      }
    }
  }
}
</style>
