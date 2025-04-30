<template>
  <section class="section-bio">
    <h2 class="heading">About <span class="heading__part">me</span></h2>
    <div class="card">
      <div class="card-img" alt="avatar image">
        <div class="card-img__ring" alt=""></div>
        <img
          :src="require('/src/assets/img/avatar.jpg')"
          class="card-img__img"
        />
      </div>
      <h3 class="card-label">Front End Web Developer</h3>
    </div>
    <div class="paragraph">
      <p class="paragraph__part">
        I'm 26 years old and since May of 2024 i have been studying web
        development.
      </p>
      <p class="paragraph__part">
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

  .heading {
    margin-top: 11svh;
    font-size: 5rem;

    &__part {
      color: var(--theme-primary);
    }
  }

  .card {
    @include vertical-flex;
    justify-content: center;
    align-items: center;
    margin: 3rem 0rem;

    &-img {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-bottom: 3rem;
      border-radius: 100%;

      &__img {
        position: absolute;
        width: 18rem;
        height: 18rem;
        border-radius: 100%;
        z-index: 10;
        border: solid 3px var(--theme-primary);
        filter: drop-shadow(0rem 0rem 1rem var(--theme-primary));
      }

      &__ring {
        width: 20rem;
        height: 20rem;
        border: solid 4px var(--theme-primary);
        border-left-color: transparent;
        border-right-color: transparent;
        border-radius: 100%;
        filter: drop-shadow(0rem 0rem 1rem var(--theme-primary));

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
    &-label {
      font-size: 3rem;
    }
  }

  .paragraph {
    max-width: 85%;
    padding: 1rem 2rem;
    font-size: 2rem;
    font-weight: 600;
    line-clamp: 5;
    white-space: break-spaces;
    text-align: center;
    border: solid 2px var(--theme-primary);
    border-radius: 10px;

    &__part:first-child {
      margin-bottom: 0.5rem;
    }

    @media screen and (max-width: 600px) {
      max-width: 75%;
    }
  }
}
</style>
