<template>
  <section class="section-projects">
    <h2 class="projects__title">Projects</h2>
    <ul class="pojects__list">
      <li>
        <div class="project-underlay-orbit"></div>
      </li>
      <li class="project project--1">
        <a
          target="_blank"
          href="https://lifepal.netlify.app/landing"
          title="LifePal Web App"
          class="project__link"
        >
          <img
            :src="require('/src/assets/img/lifepal.png')"
            alt="lifepal icon"
            class="project__img"
          />
          <h4 class="project__name">LifePal</h4>
        </a>
      </li>
      <li class="project project--2">
        <a
          target="_blank"
          href="https://samuele-verona-webdev-portfolio.netlify.app/"
          title="Old Website"
          class="project__link"
        >
          <img
            :src="require('/src/assets/img/beard.png')"
            alt="beard icon"
            class="project__img"
          />
          <h4 class="project__name">Old Website</h4>
        </a>
      </li>
      <li class="project project--3 vacant">
        <a target="_blank" class="project__link">
          <img
            :src="require('/src/assets/img/box.png')"
            alt=""
            class="project__img"
          />
          <h4 class="project__name">tba</h4>
        </a>
      </li>
      <li class="project project--4 vacant">
        <a target="_blank" class="project__link">
          <img
            :src="require('/src/assets/img/box.png')"
            alt=""
            class="project__img"
          />
          <h4 class="project__name">tba</h4>
        </a>
      </li>
    </ul>
  </section>
</template>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
@mixin vertical-flex {
  display: flex;
  flex-direction: column;
}
.section-projects {
  position: relative;
  @include vertical-flex;
  align-items: center;
  justify-content: center;

  height: 100svh;
  margin-top: 10svh;
  overflow: hidden;
  transition: all 0.5s ease;

  @media only screen and (max-width: 748px) and (orientation: landscape) {
    z-index: 10;
    height: 110svh;
    padding-bottom: 10svh;
  }

  .projects__title {
    font-size: 5rem;
    margin-top: 10svh;
  }

  .pojects__list {
    position: relative;
    height: 100%;
    width: 100%;
    list-style: none;
    background: url(/src/assets/img/layers.png);
    background-size: contain;
    background-size: 10%;
    background-repeat: no-repeat;
    background-position: center;
    overflow: visible;

    @media only screen and (max-width: 748px) and (orientation: landscape) {
      background-size: 5%;
    }

    .project {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(90deg);
      @include vertical-flex;
      width: max-content;
      z-index: 1;

      offset-path: path("M 250 0 A 250 250 0 1 0 -250 0 A 250 250 0 1 0 250 0");
      offset-anchor: 50%;
      transition: var(--transition-default);
      animation: circular 20s linear infinite, self-rotation 20s linear infinite;

      @media screen and (max-width: 600px) {
        offset-path: path(
          "M 200 0 A 200 200 0 1 0 -200 0 A 200 200 0 1 0 200 0"
        );
      }
      @media screen and (max-width: 425px) {
        offset-path: path(
          "M 150 0 A 150 150 0 1 0 -150 0 A 150 150 0 1 0 150 0"
        );
      }
      @media only screen and (max-width: 748px) and (orientation: landscape) {
        offset-path: path(
          "M 100 0 A 100 100 0 1 0 -100 0 A 100 100 0 1 0 100 0"
        );
      }

      &.project--1 {
        animation-delay: 0s;
      }
      &.project--2 {
        animation-delay: -5s;
      }
      &.project--3 {
        animation-delay: -10s;
      }
      &.project--4 {
        animation-delay: -15s;
      }

      @keyframes circular {
        0% {
          offset-distance: 0%;
        }

        100% {
          offset-distance: 100%;
        }
      }

      @keyframes self-rotation {
        0% {
          transform: rotate(90deg);
        }

        25% {
          transform: rotate(180deg);
        }

        50% {
          transform: rotate(270deg);
        }

        75% {
          transform: rotate(360deg);
        }
        100% {
          transform: rotate(450deg);
        }
      }

      .project__link {
        position: relative;
        display: flex;
        flex-direction: column;
        width: 6rem;
        aspect-ratio: 1;
        text-decoration: none;
        cursor: pointer;
        color: white;

        &:visited {
          color: white;
        }

        .project__name {
          align-self: center;
          padding-top: 0.5rem;
          font-size: 2rem;
          line-height: 2rem;
          text-align: center;
          white-space: nowrap;
        }
        @media only screen and (max-width: 748px) and (orientation: landscape) {
          width: 5rem;
        }
      }
    }
    .project-underlay-orbit {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 500px;
      height: 500px;
      content: "";
      color: rgba(255, 255, 255, 0.233);
      border-radius: 100%;
      border: solid 1px;
      z-index: 0;
      box-shadow: 0rem 0rem 0.9rem var(--theme-primary),
        0rem 0.2rem 0.9rem var(--theme-primary);
      filter: drop-shadow(0rem 0.2rem 0.9rem var(--theme-primary));
      transition: var(--transition-default);

      @media screen and (max-width: 600px) {
        width: 400px;
        height: 400px;
      }
      @media screen and (max-width: 425px) {
        width: 300px;
        height: 300px;
      }
      @media only screen and (max-width: 748px) and (orientation: landscape) {
        width: 200px;
        height: 200px;
      }
    }
  }
}
</style>
