<template>
  <section class="home-page">
    <div class="img">
      <img
        :src="require('/src/assets/img/top-layer.png')"
        class="img__layer img__layer--top"
      />
      <img
        :src="require('/src/assets/img/middle-layer.png')"
        class="img__layer img__layer--middle"
      />
      <img
        :src="require('/src/assets/img/bottom-layer.png')"
        class="img__layer img__layer--bottom"
      />
    </div>
    <div class="hero">
      <h2 class="hero__title">Hi, i'm Sam</h2>
      <h3 class="hero__subtitle">Front End Web Developer</h3>
      <p class="hero__paragraph">
        Welcome!<br />I am a starting Web Developer and this is my portfolio
        website.
      </p>
      <div class="links-box">
        <a
          target="_blank"
          href="https://github.com/SamueleVerona"
          title="GitHub"
          class="link link--1"
        >
          <img
            :src="require('/src/assets/img/github-icon.png')"
            alt="github icon"
            class="link__img"
          />
        </a>
        <a
          target="_blank"
          href="https://www.linkedin.com/in/samuele-verona-1820342b1/"
          title="LinkedIn"
          class="link link--2"
        >
          <img
            :src="require('/src/assets/img/linkedin-icon.png')"
            alt="linkedin icon"
            class="link__img"
          />
        </a>
      </div>
    </div>
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
.home-page {
  position: relative;
  display: flex;
  justify-content: flex-start;
  height: 90lvh;
  transition: all 1s ease;
}
.img {
  position: absolute;
  right: 4%;
  bottom: 42%;
  transform: translateY(50%);
  width: 50%;
  max-width: 50rem;
  aspect-ratio: 1;

  &__layer {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;

    &--top {
      z-index: 5;
      filter: drop-shadow(0rem 0.5rem 0.6rem rgb(28, 27, 27));
      filter: saturate(90%);
      animation: sandwich 2s cubic-bezier(0.075, 0.82, 0.165, 1) infinite
        alternate;
      transform: translate(-50%, calc(-50% + 10px));
    }

    &--middle {
      z-index: 4;
      filter: drop-shadow(0rem 0.5rem 0.6rem rgba(0, 0, 0, 0.195));
    }
    &--bottom {
      z-index: 3;
      transform: translate(-50%, calc(-50% - 10px));
      filter: drop-shadow(0rem 0.5rem 1rem rgba(0, 0, 0, 0.371));
      animation: sandwich 2s cubic-bezier(0.6, 0.04, 0.98, 0.335) infinite
        alternate-reverse;
    }
  }
  @media screen and (max-width: 600px) {
    bottom: -5%;
    left: 70%;
    transform: translateX(-50%);
    width: 40%;
  }

  @keyframes sandwich {
    0% {
      top: 50%;
    }
    100% {
      top: calc(50% - 10px);
    }
  }
}
.hero {
  position: relative;

  @include vertical-flex;
  justify-content: center;
  align-items: center;
  width: 70%;
  padding: 0rem 5rem;
  z-index: 1;
  text-align: left;

  @media screen and (max-width: 600px) {
    width: 100%;
  }

  &__title {
    width: 100%;
    font-size: 8rem;
    line-height: 8rem;
    margin-bottom: 1rem;
    white-space: nowrap;
  }
  &__subtitle {
    position: relative;
    align-self: flex-start;
    max-width: 40rem;
    margin-bottom: 2rem;
    font-size: 3.5rem;
    text-overflow: clip;
    white-space: nowrap;
    color: var(--theme-primary);
    border-right: solid 2px;
    background: var(--theme-primary);
    background-clip: text;
    background-repeat: no-repeat;
    background-size: cover;
    -moz-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;

    animation: typing 3s cubic-bezier(0.47, 0, 0.745, 0.715) infinite alternate,
      blink 0.15s cubic-bezier(0.47, 0, 0.745, 0.715) infinite alternate;
    @keyframes typing {
      0% {
        width: 100%;
      }

      100% {
        width: 0%;
      }
    }
    @keyframes blink {
      0% {
        border-color: rgba(255, 255, 255, 0);
      }

      100% {
        border-color: inherit;
      }
    }
  }

  &__paragraph {
    width: 100%;
    font-size: 3rem;
    font-weight: 400;
    line-height: 3.5rem;
    line-clamp: 3;
  }

  .links-box {
    position: absolute;
    bottom: 15%;
    align-self: flex-start;
    transition: var(--transition-default);

    @media screen and (max-width: 500px) {
      bottom: 20%;

      &__img {
        width: 4rem;
        height: 4rem;
      }
    }
    @media only screen and (max-height: 748px) and (orientation: landscape) {
      bottom: 5%;
      &__img {
        width: 3rem;
        height: 3rem;
      }
    }
    @media only screen and (max-height: 426px) and (orientation: landscape) {
      bottom: 0%;
    }
  }
  .link {
    height: 100%;
    cursor: pointer;

    &--1 {
      margin-right: 2rem;
    }

    &__img {
      width: 5rem;
      height: 5rem;
      filter: invert(100%);
      transition: var(--transition-default);

      &:hover {
        scale: 1.1;
      }
    }

    @media screen and (max-width: 500px) {
      width: 4rem;
      height: 4rem;
    }
    @media only screen and (max-height: 748px) and (orientation: landscape) {
      width: 3rem;
      height: 3rem;
    }
  }
}
</style>
