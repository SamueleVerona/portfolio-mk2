<template>
  <section class="projects-page">
    <h2 class="heading">Projects</h2>
    <ul class="projects-list">
      <div class="projects-list-shape" inert></div>
      <li class="project project--1">
        <a
          target="_blank"
          href="https://lifepal.netlify.app/landing"
          title="LifePal Web App"
          class="project__link"
        >
        </a>
        <img
          :src="require('/src/assets/img/lifepal.png')"
          alt="lifepal icon"
          class="project__img"
          inert
        />
        <h4 class="project__name">LifePal</h4>
      </li>
      <li class="project project--2">
        <a
          target="_blank"
          href="https://samuele-verona-webdev-portfolio.netlify.app/"
          title="Old Website"
          class="project__link"
        ></a>
        <img
          :src="require('/src/assets/img/beard.webp')"
          alt="beard icon"
          class="project__img"
          inert
        />
        <h4 class="project__name">Old Website</h4>
      </li>
      <li class="project project--3">
        <a
          target="_blank"
          href="https://crochet-ecom.netlify.app/"
          class="project__link"
        >
        </a>
        <img
          :src="require('/src/assets/img/crochet.png')"
          alt=""
          class="project__img"
          inert
        />
        <h4 class="project__name">Ecom Concept</h4>
      </li>
      <li class="project project--4 vacant">
        <a
          target="_blank"
          href="https://lifepal-svelte.netlify.app"
          class="project__link"
        >
        </a>
        <img
          :src="require('/src/assets/img/svelte.png')"
          alt=""
          class="project__img"
          inert
        />
        <h4 class="project__name">LifePal Svelte</h4>
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
.projects-page {
  position: relative;
  @include vertical-flex;
  align-items: center;
  justify-content: center;

  height: 100svh;
  margin-top: 10svh;
  overflow: visible;
  transition: all 0.5s ease;

  @media only screen and (max-width: 748px) and (orientation: landscape) {
    z-index: 10;
    height: 110svh;
    padding-bottom: 10svh;
  }
}
.heading {
  font-size: 5rem;
  margin-top: 10svh;
}
$offset: 25%;

.projects-list {
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

  &:has(li:hover) {
    li:not(:hover) {
      offset-distance: 82.5%;
    }
  }

  @media only screen and (max-width: 748px) and (orientation: landscape) {
    background-size: 5%;
  }

  &-shape {
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

.project {
  @include vertical-flex;
  width: max-content;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;
  color: rgba(255, 255, 255, 0.233);
  border-radius: 100%;
  filter: drop-shadow(0rem 0rem 0.5rem rgb(249, 242, 255));

  transition: var(--transition-default);
  cursor: pointer;

  offset-path: path("M 250 0 A 250 250 0 1 0 -250 0 A 250 250 0 1 0 250 0");
  offset-anchor: 105%;
  transition: all 0.8s ease;
  width: 6rem;
  height: 6rem;

  &__img {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 60%;
    height: 60%;
    object-fit: contain;
    transform: translate(-50%, -50%);
    transition: all 0.6s ease;
    opacity: 0;
    filter: brightness(150%);
  }

  &__name {
    position: absolute;
    bottom: -50%;
    left: 50%;
    transform: translateX(-50%);
    font-size: 3rem;
    opacity: 0;
    color: white;
    white-space: nowrap;
    transition: all 1s ease;
  }

  &:hover {
    width: 10rem;
    height: 10rem;
    filter: drop-shadow(0rem 0rem 0.2rem rgb(249, 242, 255));
    offset-anchor: 100%;

    & .project__name,
    .project__img {
      opacity: 1;
    }
  }

  &.project--1 {
    background: radial-gradient(
      circle at 100%,
      rgb(39, 205, 175),
      rgb(180, 130, 238)
    );
    transform: rotate(90deg);
  }
  &.project--2 {
    offset-distance: 25%;
    background: radial-gradient(
      circle at 100%,
      rgb(122, 28, 210),
      rgb(255, 255, 255),
      rgb(162, 95, 7)
    );
    transform: rotate(180deg);
    animation-delay: -5s;
  }
  &.project--3 {
    background: radial-gradient(
      circle at 100%,
      rgb(116, 21, 70),
      rgb(224, 167, 182),
      rgb(96, 136, 36)
    );
    transform: rotate(-90deg);
    offset-distance: 50%;
    animation-delay: -10s;
  }
  &.project--4 {
    background: radial-gradient(
      circle at 100%,
      rgb(239, 83, 31),
      rgb(87, 199, 233)
    );
    transform: rotate(0deg);
    offset-distance: 75%;
    animation-delay: -15s;
  }

  @media screen and (max-width: 600px) {
    offset-path: path("M 200 0 A 200 200 0 1 0 -200 0 A 200 200 0 1 0 200 0");
  }
  @media screen and (max-width: 425px) {
    offset-path: path("M 150 0 A 150 150 0 1 0 -150 0 A 150 150 0 1 0 150 0");
  }
  @media only screen and (max-width: 748px) and (orientation: landscape) {
    offset-path: path("M 100 0 A 100 100 0 1 0 -100 0 A 100 100 0 1 0 100 0");
  }

  &__link {
    position: relative;
    display: flex;
    flex-direction: column;
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
</style>
