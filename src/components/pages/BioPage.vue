<template>
  <section class="section-bio">
    <h2 class="bio__title">About <span class="sub-text">me</span></h2>
    <div class="bio__card">
      <div alt="avatar-image" class="card__img">
        <img
          :src="require('/src/assets/img/circle.png')"
          class="img__ring"
          alt=""
        />
        <img :src="require('/src/assets/img/avatar.jpg')" class="img__avatar" />
      </div>
      <h3 class="card__label">Front End Web Developer</h3>
    </div>
    <div class="bio__desc">
      <p class="bio__desc-subsection">
        I'm 26 years old and since May of 2024 i have been studying web
        development.
      </p>
      <p class="bio__desc-subsection">
        Here you can find information about my journey and have a look at my
        most recent projects and codebase. Check out the 'projects' section to
        see more!
      </p>
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
.section-bio {
  @include vertical-flex;
  justify-content: center;
  align-items: center;
  min-height: 100svh;
  margin-top: 10svh;
  text-align: center;
  transition: all 1s ease;

  .bio__title {
    margin-top: 11svh;
    font-size: 5rem;

    .sub-text {
      color: var(--theme-primary);
    }
  }

  .bio__card {
    @include vertical-flex;
    justify-content: center;
    align-items: center;
    margin: 3rem 0rem;

    .card__img {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-bottom: 3rem;
      border-radius: 100%;

      .img__avatar {
        position: absolute;
        width: 18rem;
        height: 18rem;
        border-radius: 100%;
        z-index: 10;
        border: solid 3px var(--theme-primary);
      }

      .img__ring {
        width: 20rem;
        height: 20rem;
        filter: drop-shadow(0rem 0rem 0.6rem var(--theme-primary));
        animation: rotation 5s linear infinite;
      }

      @keyframes rotation {
        0% {
          rotate: 0deg;
        }
        100% {
          rotate: 360deg;
        }
      }
    }
    .card__label {
      font-size: 3rem;
    }
  }

  .bio__desc {
    max-width: 85%;
    padding: 1rem 2rem;
    font-size: 2rem;
    font-weight: 600;
    line-clamp: 5;
    white-space: break-spaces;
    text-align: center;
    border: solid 2px var(--theme-primary);
    border-radius: 10px;

    .bio__desc-subsection:first-child {
      margin-bottom: 0.5rem;
    }

    @media screen and (max-width: 600px) {
      max-width: 75%;
    }
  }
}
</style>
