<template>
  <section class="section-timeline">
    <h2 class="timeline__title">My journey</h2>
    <section class="timeline__events">
      <section class="list-wrapper list--education">
        <h3 class="list__title">Education</h3>
        <ul class="events__list">
          <li class="event">
            <h4 class="event__date">2012-2017</h4>
            <h3 class="event__title">High School Graduation</h3>
            <p class="event__text">Graduated in chemistry and biotechnology</p>
          </li>
          <li class="event">
            <h4 class="event__date">2019-2022</h4>
            <h3 class="event__title">Bachelor's degree</h3>
            <p class="event__text">
              Graduated in 'Electronic Music and New Technologies' in
              Conservatory
            </p>
          </li>
          <li class="event">
            <h4 class="event__date">2024-2024</h4>
            <h3 class="event__title">WebDev Certificates</h3>
            <p class="event__text">
              Attended Boolean's 'Web Development Fundamentals Camp ad Udemy's '
              The Complete JavaScript Course: From Zero to Expert' and 'Vue -
              The Complete Guide'
            </p>
          </li>
        </ul>
      </section>

      <section class="list-wrapper list--experience">
        <h3 class="list__title">Experience</h3>
        <ul class="events__list">
          <li class="event">
            <h4 class="event__date">2018-2019</h4>
            <h3 class="event__title">Warehouse worker</h3>
            <p class="event__text">
              Worked for 'Serivtù s.r.l.' as both a warehouse worker and
              delivery man
            </p>
          </li>
          <li class="event">
            <h4 class="event__date">2022-2024</h4>
            <h3 class="event__title">Warehouse worker</h3>
            <p class="event__text">
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
.section-timeline {
  min-height: 100dvh;
  display: flex;
  flex-direction: column;
  align-items: center;

  .timeline__title {
    flex: 1;
    font-size: 5rem;
  }

  .timeline__events {
    flex: 1;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: flex-start;
    justify-content: space-evenly;
    padding: 5rem 1rem;

    .list-wrapper {
      display: flex;
      flex-direction: column;
      max-width: 45%;
      height: 60%;
      padding-bottom: 1rem;
      flex: 1;

      .list__title {
        display: inline-block;
        font-size: 3rem;
        padding: 1rem 0rem 1rem 1rem;
        margin: 1rem 1rem 1rem 1rem;
        text-align: left;
      }

      .events__list {
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        list-style: none;
        border-left: solid 2px rgb(0, 170, 255);

        .event {
          position: relative;
          padding: 3rem;
          margin: 0.5rem 1rem;
          text-align: left;
          overflow: visible;

          border: solid 2px rgb(0, 170, 255);
          border-radius: 10px;
          .event__date {
            font-size: 2rem;
          }
          .event__title {
            font-size: 2rem;
          }
          .event__text {
            font-size: 1.8rem;
            font-weight: 600;
          }

          &::after {
            position: absolute;
            left: -2rem;
            top: 50%;
            width: 1.5rem;
            aspect-ratio: 1;
            border-radius: 100%;
            content: "";
            background: rgb(3, 141, 255);
          }
        }
      }
    }
    @media screen and (max-width: 748px) {
      flex-direction: column;
      align-items: center;

      .list-wrapper {
        max-width: 90%;
        .list--education {
          margin: 0rem 0rem 2rem 0rem;
        }
      }
    }
  }
}
</style>
