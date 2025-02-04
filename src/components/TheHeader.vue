<template>
  <header class="global-header">
    <img
      :src="require('/src/assets/img/logo-icon.png')"
      alt=""
      width="50"
      class="site-logo"
    />
    <nav class="navbar" @click="handleNavigation">
      <ul class="pages-list">
        <li class="pages-list__item">
          <img
            :src="require('/src/assets/img/home.png')"
            alt="home icon"
            class="pages-list__img"
            data-btn-id="home"
          />
          <button class="pages-list__btn" data-btn-id="home">Home</button>
        </li>
        <li class="pages-list__item">
          <img
            :src="require('/src/assets/img/bio.png')"
            alt="avatar icon"
            class="pages-list__img"
            data-btn-id="bio"
          />
          <button class="pages-list__btn" data-btn-id="bio">Bio</button>
        </li>
        <li class="pages-list__item">
          <img
            :src="require('/src/assets/img/path.png')"
            alt="path icon"
            class="pages-list__img"
            data-btn-id="time"
          />
          <button class="pages-list__btn" data-btn-id="time">Path</button>
        </li>
        <li class="pages-list__item">
          <img
            :src="require('/src/assets/img/projects.png')"
            alt="projects icon"
            class="pages-list__img"
            data-btn-id="projects"
          />
          <button class="pages-list__btn" data-btn-id="projects">
            Projects
          </button>
        </li>
        <li class="pages-list__item">
          <img
            :src="require('/src/assets/img/links.png')"
            alt="links icon"
            class="pages-list__img"
            data-btn-id="links"
          />
          <button class="pages-list__btn" data-btn-id="links">Links</button>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
function handleNavigation(e) {
  const target = e.target;

  if (!target.dataset.btnId) return;

  const sectionTarget = target.dataset.btnId;
  document
    .querySelector(`#${sectionTarget}`)
    .scrollIntoView({ behavior: "smooth", block: "start" });
}
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.global-header {
  position: sticky;
  top: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  height: 10vh;
  overflow: visible;
  backdrop-filter: blur(10px);
  box-shadow: 0rem 0rem 0.8rem aqua;
  pointer-events: auto;
  z-index: 100;

  .site-logo {
    margin-left: 1rem;
  }

  .navbar {
    display: flex;
    height: 100%;
    margin-right: 3rem;

    .pages-list {
      position: relative;
      flex: 1;
      display: flex;
      justify-content: space-between;
      align-items: center;
      list-style: none;
      height: 100%;

      .pages-list__img {
        display: none;
        width: 3.5rem;
        aspect-ratio: 1;
        margin: 0 1rem;
        padding: 0;
        cursor: pointer;
        transition: var(--transition-default);

        &:hover {
          scale: 1.2;
        }
      }

      .pages-list__btn {
        display: block;
        margin: 0rem 1.5rem;
        text-decoration: none;
        font-size: 2.5rem;
        font-weight: 600;
        cursor: pointer;
        background: transparent;
        border: none;
        color: inherit;
        font-family: inherit;
        transition: var(--transition-default);
        &:hover {
          color: var(--theme-primary);
        }

        @keyframes fade-in {
          0% {
            transform: translateY(-20px);
            opacity: 0;
          }
          100% {
            transform: translateY(0);

            opacity: 1;
          }
        }
      }
    }

    @media screen and (max-width: 748px) {
      align-items: center;
      justify-content: flex-end;
      width: max-content;

      .pages-list.hidden {
        display: none;
      }
      .pages-list {
        .pages-list__img {
          display: block;
          width: 3rem;
          aspect-ratio: 1;
        }
        .pages-list__btn {
          display: none;
        }
      }
    }
  }
}
</style>
