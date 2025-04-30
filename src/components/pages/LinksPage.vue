<template>
  <section class="links-page">
    <h2 class="heading">Useful <span class="heading__part">Links</span></h2>
    <ul class="links-list">
      <li class="link-card link-card--1">
        <a
          target="_blank"
          href="https://github.com/SamueleVerona"
          title="GitHub"
          class="link-card__link"
        >
          <img
            :src="require('/src/assets/img/github-icon.png')"
            alt="github icon"
            class="link-card__img"
          />
          <h4 class="link-card__name">GitHub</h4>
        </a>
      </li>
      <li class="link-card link-card--2">
        <a
          target="_blank"
          href="https://www.linkedin.com/in/samuele-verona-1820342b1/"
          title="LinkediIn"
          class="link-card__link"
        >
          <img
            :src="require('/src/assets/img/linkedin-icon.png')"
            alt="linkedin icon"
            class="link-card__img"
          />
          <h4 class="link-card__name">LinkedIn</h4>
        </a>
      </li>
      <li class="link-card link-card--3">
        <a
          target="_blank"
          href="https://youtube.com/@lsmusic1975?si=V9cFoydsu9Q5feFy"
          title="YouTube"
          class="link-card__link"
        >
          <img
            :src="require('/src/assets/img/youtube-icon.png')"
            alt="youtube icon"
            class="link-card__img"
          />
          <h4 class="link-card__name">Side Project</h4>
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
  justify-content: center;
}
.links-page {
  position: relative;
  @include vertical-flex;
  align-items: center;
  justify-content: center;
  height: 90svh;
  margin-top: 10svh;
  transition: all 1s ease;
}
.heading {
  font-size: 5rem;
  .heading__part {
    color: var(--theme-primary);
  }
}
.links-list {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  width: 100%;
  height: 100%;

  @media screen and (max-width: 600px) {
    flex-direction: column;
  }
}
.link-card {
  @include vertical-flex;
  align-items: center;
  justify-content: center;
  flex: 1;

  &__link {
    @include vertical-flex;
    justify-content: center;
    align-items: center;
    width: max-content;
    height: 100%;
    text-decoration: none;
    transition: var(--transition-default);

    &:hover {
      scale: 1.2;
      .link-card__name {
        color: var(--theme-primary);
      }
    }
  }
  &__img {
    width: 8rem;
    height: auto;
    filter: invert(100%);
  }

  &__name {
    font-size: 2.5rem;
    text-align: center;
    color: white;
    transition: var(--transition-default);
  }
}
</style>
