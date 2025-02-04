<template>
  <section class="section-contacts">
    <h2 class="section-contacts__title">
      Useful <span class="sub-text">Links</span>
    </h2>
    <ul class="contacts__list">
      <li class="contact contact--1">
        <a
          target="_blank"
          href="https://github.com/SamueleVerona"
          title="GitHub"
          class="contact__link"
        >
          <img
            :src="require('/src/assets/img/github-icon.png')"
            alt="github icon"
            class="contact__img"
          />
          <h4 class="contact__name">GitHub</h4>
        </a>
      </li>
      <li class="contact contact--2">
        <a
          target="_blank"
          href="https://www.linkedin.com/in/samuele-verona-1820342b1/"
          title="LinkediIn"
          class="contact__link"
        >
          <img
            :src="require('/src/assets/img/linkedin-icon.png')"
            alt="linkedin icon"
            class="contact__img"
          />
          <h4 class="contact__name">LinkedIn</h4>
        </a>
      </li>
      <li class="contact contact--3">
        <a
          target="_blank"
          href="https://youtube.com/@lsmusic1975?si=V9cFoydsu9Q5feFy"
          title="YouTube"
          class="contact__link"
        >
          <img
            :src="require('/src/assets/img/youtube-icon.png')"
            alt="youtube icon"
            class="contact__img"
          />
          <h4 class="contact__name">Side Project</h4>
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
.section-contacts {
  position: relative;
  @include vertical-flex;
  align-items: center;
  justify-content: center;
  height: 90svh;
  margin-top: 10svh;
  transition: all 1s ease;

  .section-contacts__title {
    font-size: 5rem;
    .sub-text {
      color: var(--theme-primary);
    }
  }

  .contacts__list {
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    width: 100%;
    height: 100%;

    .contact {
      @include vertical-flex;
      align-items: center;
      justify-content: center;
      flex: 1;

      .contact__link {
        @include vertical-flex;
        justify-content: center;
        align-items: center;
        width: max-content;
        height: 100%;
        text-decoration: none;
        transition: var(--transition-default);

        &:hover {
          scale: 1.2;
          .contact__name {
            color: var(--theme-primary);
          }
        }

        .contact__img {
          width: 8rem;
          height: auto;
          filter: invert(100%);
        }

        .contact__name {
          font-size: 2.5rem;
          text-align: center;
          color: white;
          transition: var(--transition-default);
        }
      }
    }

    @media screen and (max-width: 600px) {
      flex-direction: column;
    }
  }
}
</style>
