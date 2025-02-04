<template>
  <section class="section-timeline">
    <h2 class="timeline__title">My <span class="sub-text">path</span></h2>
    <section class="timeline__events">
      <section class="list-section list-section--education">
        <h3 class="list-section__title">Education</h3>
        <ul class="list-section__list">
          <li class="list-section__event">
            <h4 class="list-section__event-date">2012-2017</h4>
            <h3 class="list-section__event-title">High School Graduation</h3>
            <p class="list-section__event-desc">
              Graduated in "Chemistry and Biotechnologies"
            </p>
          </li>
          <li class="list-section__event">
            <h4 class="list-section__event-date">2019-2022</h4>
            <h3 class="list-section__event-title">Bachelor's degree</h3>
            <p class="list-section__event-desc">
              Graduated in "Electronic Music and New Technologies" in
              Conservatory
            </p>
          </li>
          <li class="list-section__event">
            <h4 class="list-section__event-date">2024-2024</h4>
            <h3 class="list-section__event-title">WebDev Certificates</h3>
            <p class="list-section__event-desc">
              Attended Boolean's "Web Development Fundamentals Camp" and Udemy's
              "The Complete JavaScript Course: From Zero to Expert" and "Vue -
              The Complete Guide"
            </p>
          </li>
        </ul>
      </section>
      <section class="list-section list-section--experience">
        <h3 class="list-section__title">Experience</h3>
        <ul class="list-section__list">
          <li class="list-section__event">
            <h4 class="list-section__event-date">2018-2019</h4>
            <h3 class="list-section__event-title">Warehouse worker</h3>
            <p class="list-section__event-desc">
              Worked for 'Serivtù s.r.l.' as both a warehouse worker and
              delivery man
            </p>
          </li>
          <li class="list-section__event">
            <h4 class="list-section__event-date">2022-2024</h4>
            <h3 class="list-section__event-title">Warehouse worker</h3>
            <p class="list-section__event-desc">
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
.section-timeline {
  @include vertical-flex;
  align-items: center;
  justify-content: center;
  min-height: 10svh;
  scroll-snap-align: start;

  transition: all 1s ease;

  @media only screen and (max-height: 748px) and (orientation: landscape) {
  }

  .timeline__title {
    font-size: 5rem;
    margin-top: 10svh;

    .sub-text {
      color: var(--theme-primary);
    }
  }

  .timeline__events {
    display: flex;
    align-items: flex-start;
    justify-content: space-evenly;
    width: 100%;
    height: 100%;
    padding: 5rem 1rem;

    .list-section {
      @include vertical-flex;
      max-width: 45%;
      height: 60%;
      padding-bottom: 1rem;
      padding-left: 1rem;

      .list-section__title {
        padding: 1rem 0rem 1rem 1rem;
        margin: 1rem;
        font-size: 3rem;
        text-align: left;
      }

      .list-section__list {
        @include vertical-flex;
        justify-content: space-evenly;
        list-style: none;
        border-left: solid 2px var(--theme-primary);

        .list-section__event {
          position: relative;
          display: flex;
          flex-direction: column;
          justify-content: center;

          padding: 3rem;
          margin: 0.5rem 1rem;
          text-align: left;
          border: solid 2px var(--theme-primary);
          border-radius: 10px;

          .list-section__event-date {
            font-size: 2rem;
            color: var(--theme-primary);
          }
          .list-section__event-title {
            font-size: 2.2rem;
          }
          .list-section__event-desc {
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
      }
    }
    @media screen and (max-width: 748px) {
      flex-direction: column;
      align-items: center;

      .list-section {
        max-width: 90%;

        &.list-section--education {
          margin: 0rem 0rem 2rem 0rem;
        }
      }
    }
  }
}
</style>
