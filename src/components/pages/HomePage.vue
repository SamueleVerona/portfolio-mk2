<template>
  <section class="section">
    <div class="section__abstract">
      <h2 class="bio__title">Hi, i'm Sam</h2>
      <h3 class="bio__subtitle">Front End Web Developer</h3>
      <p class="bio__desc">
        Welcome!<br />I am a starting Web Developer and this is my portfolio
        website.
      </p>
    </div>
    <div class="img-frame"></div>
  </section>
</template>

<style lang="scss" scoped>
.section {
  display: flex;
  position: relative;
  justify-content: flex-start;
  height: 90dvh;

  .section__abstract {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: left;
    width: 70%;
    padding: 0rem 5rem;
    z-index: 1;

    @media screen and (max-width: 600px) {
      width: 100%;
    }

    .bio__title {
      width: 100%;
      font-size: 6rem;
      line-height: 6rem;
      margin-bottom: 1rem;
    }
    .bio__subtitle {
      width: 100%;
      margin-bottom: 2rem;

      font-size: 3rem;
    }
    .bio__desc {
      font-size: 3rem;
      text-anchor: start;
      line-clamp: 3;
    }
  }
  .img-frame {
    position: absolute;
    right: 5%;
    bottom: 50%;
    transform: translateY(50%);
    width: 45%;
    max-width: 40rem;
    // z-index: -1;
    aspect-ratio: 1;
    background: url(/src/assets/img/layers.png);
    background-size: cover;
    background-position: center;
    @media screen and (max-width: 600px) {
      bottom: -15%;
      left: 50%;
      transform: translateX(-50%);
    }
  }
}
</style>
