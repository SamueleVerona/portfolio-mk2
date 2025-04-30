<template>
  <header class="header">
    <img
      :src="require('/src/assets/img/logo-icon.png')"
      alt=""
      width="50"
      class="logo"
    />
    <nav class="navbar" @click="handleNavigation">
      <ul class="pages-list">
        <li class="page-link">
          <img
            :src="require('/src/assets/img/home.png')"
            alt="home icon"
            class="page-link__icon"
            data-btn-id="home"
          />
          <button class="page-link__btn" data-btn-id="home">Home</button>
        </li>
        <li class="page-link">
          <img
            :src="require('/src/assets/img/bio.png')"
            alt="avatar icon"
            class="page-link__icon"
            data-btn-id="bio"
          />
          <button class="page-link__btn" data-btn-id="bio">Bio</button>
        </li>
        <li class="page-link">
          <img
            :src="require('/src/assets/img/path.png')"
            alt="path icon"
            class="page-link__icon"
            data-btn-id="time"
          />
          <button class="page-link__btn" data-btn-id="time">Path</button>
        </li>
        <li class="page-link">
          <img
            :src="require('/src/assets/img/projects.png')"
            alt="projects icon"
            class="page-link__icon"
            data-btn-id="projects"
          />
          <button class="page-link__btn" data-btn-id="projects">
            Projects
          </button>
        </li>
        <li class="page-link">
          <img
            :src="require('/src/assets/img/links.png')"
            alt="links icon"
            class="page-link__icon"
            data-btn-id="links"
          />
          <button class="page-link__btn" data-btn-id="links">Links</button>
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

.header {
  position: sticky;
  top: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  min-height: 10vh;
  height: max-content;
  overflow: visible;
  backdrop-filter: blur(10px);
  box-shadow: 0rem 0rem 0.8rem aqua;
  pointer-events: auto;
  z-index: 100;
}

.logo {
  margin-left: 1rem;
}

.navbar {
  display: flex;
  height: 100%;
  margin-right: 3rem;

  @media screen and (max-width: 748px) {
    align-items: center;
    justify-content: flex-end;
    width: max-content;

    .pages-list.hidden {
      display: none;
    }
    .pages-list {
      .page-link__icon {
        display: block;
        width: 3rem;
        aspect-ratio: 1;
      }
      .page-link__btn {
        display: none;
      }
    }
  }
}

.pages-list {
  position: relative;
  flex: 1;
  display: flex;
  justify-content: space-between;
  align-items: center;
  list-style: none;
  height: 100%;

  @media screen and (max-width: 748px) {
    &.hidden {
      display: none;
    }
  }
}

.page-link {
  &__icon {
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

  &__btn {
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

  @media screen and (max-width: 748px) {
    &__icon {
      display: block;
      width: 3rem;
      aspect-ratio: 1;
    }
    &__btn {
      display: none;
    }
  }
}
</style>
