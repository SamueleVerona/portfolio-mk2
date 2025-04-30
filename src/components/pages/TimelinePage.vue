<template>
  <section class="timeline-page">
    <h2 class="heading">My <span class="heading__part">path</span></h2>
    <section class="events-box">
      <section class="events-section events-section--education">
        <h3 class="events-section__title">Education</h3>
        <ul class="events-section__list">
          <li class="event">
            <h4 class="event__date">2012-2017</h4>
            <h3 class="event__title">High School Graduation</h3>
            <p class="event__paragraph">
              Graduated in "Chemistry and Biotechnologies"
            </p>
          </li>
          <li class="event">
            <h4 class="event__date">2019-2022</h4>
            <h3 class="event__title">Bachelor's degree</h3>
            <p class="event__paragraph">
              Graduated in "Electronic Music and New Technologies" in
              Conservatory
            </p>
          </li>
          <li class="event">
            <h4 class="event__date">2024-2024</h4>
            <h3 class="event__title">WebDev Certificates</h3>
            <p class="event__paragraph">
              Attended Boolean's "Web Development Fundamentals Camp" and Udemy's
              "The Complete JavaScript Course: From Zero to Expert" and "Vue -
              The Complete Guide"
            </p>
          </li>
        </ul>
      </section>
      <section class="events-section events-section--experience">
        <h3 class="events-section__title">Experience</h3>
        <ul class="events-section__list">
          <li class="event">
            <h4 class="event__date">2018-2019</h4>
            <h3 class="event__title">Warehouse worker</h3>
            <p class="event__paragraph">
              Worked for 'Serivtù s.r.l.' as both a warehouse worker and
              delivery man
            </p>
          </li>
          <li class="event">
            <h4 class="event__date">2022-2024</h4>
            <h3 class="event__title">Warehouse worker</h3>
            <p class="event__paragraph">
              Worked for 'Fratelli Foschiani s.r.l.' as both a warehouse worker
              and delivery man
            </p>
          </li>
        </ul>
      </section>
    </section>
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

.timeline-page {
  @include vertical-flex;
  align-items: center;
  justify-content: center;
  min-height: 10svh;
  scroll-snap-align: start;
  transition: all 1s ease;

  @media only screen and (max-height: 748px) and (orientation: landscape) {
  }
}

.heading {
  font-size: 5rem;
  margin-top: 10svh;

  .heading__part {
    color: var(--theme-primary);
  }
}

.events-box {
  display: flex;
  align-items: flex-start;
  justify-content: space-evenly;
  width: 100%;
  height: 100%;
  padding: 5rem 1rem;

  @media screen and (max-width: 748px) {
    flex-direction: column;
    align-items: center;
  }
}

.events-section {
  @include vertical-flex;
  max-width: 45%;
  height: 60%;
  padding-bottom: 1rem;
  padding-left: 1rem;

  &__title {
    padding: 1rem 0rem 1rem 1rem;
    margin: 1rem;
    font-size: 3rem;
    text-align: left;
  }

  &__list {
    @include vertical-flex;
    justify-content: space-evenly;
    list-style: none;
    border-left: solid 2px var(--theme-primary);
  }

  &--education {
    @media screen and (max-width: 748px) {
      margin: 0rem 0rem 2rem 0rem;
    }
  }

  @media screen and (max-width: 748px) {
    max-width: 90%;
  }
}

.event {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;

  padding: 3rem;
  margin: 0.5rem 1rem;
  text-align: left;
  border: solid 2px var(--theme-primary);
  border-radius: 10px;

  &__date {
    font-size: 2rem;
    color: var(--theme-primary);
  }
  &__title {
    font-size: 2.2rem;
  }
  &__paragraph {
    font-size: 2rem;
    font-weight: 400;
    line-height: 2.2rem;
  }

  &::after {
    position: absolute;
    left: -2.1rem;
    top: 50%;
    width: 1.5rem;
    aspect-ratio: 1;
    content: "";
    border-radius: 100%;
    background: var(--theme-primary);
  }
}
</style>
