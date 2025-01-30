<template>
  <header class="global-header">
    <h2 class="site-logo">Samuele Verona</h2>
    <nav class="navbar" @click="toggleMenu">
      <button class="menu-btn link"></button>
      <ul class="site__link-list hidden">
        <li class="site__page">
          <a class="link">Home</a>
        </li>
        <li class="site__page">
          <a class="link">Bio</a>
        </li>
        <li class="site__page">
          <a class="link">Journey</a>
        </li>
        <li class="site__page">
          <a class="link">Projects</a>
        </li>
        <li class="site__page">
          <a class="link">Contacts</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
function toggleMenu(e) {
  const target = e.target;
  if (!target.classList.contains("menu-btn")) return;
  const menu = target.nextElementSibling;
  console.log(menu);
  menu.classList.toggle("hidden");
}
</script>

<style lang="scss" scoped>
.global-header {
  position: relative;
  display: flex;
  justify-content: space-between;
  padding: 1rem;
  height: 10dvh;
  overflow: visible;

  .site-logo {
    flex: 2;
    display: flex;
    align-items: center;
    font-size: 4rem;
    padding: 0;
    padding-left: 2rem;
  }
  .menu-btn {
    flex: 1;
    display: none;
    height: 100%;
    aspect-ratio: 1;
    margin-right: 1rem;
    background: url(/src/assets/img/menu.png);
    background-size: 70%;
    background-repeat: no-repeat;
    background-position: center;
    border: none;
    filter: invert(100%);
    cursor: pointer;

    @media screen and (max-width: 748px) {
      display: block;
      flex-direction: column;
      flex: 0.5;
      align-items: flex-end;
    }
  }

  .site__link-list {
    position: relative;
    flex: 1;
    display: flex;
    justify-content: space-between;
    align-items: center;
    list-style: none;
    height: 100%;

    .link {
      margin: 0rem 0.5rem;
      text-decoration: none;
      cursor: pointer;
      font-size: 2.2rem;
      font-weight: 600;

      @keyframes fade-in {
        0% {
          opacity: 0;
        }
        100% {
          opacity: 1;
        }
      }
    }

    @media screen and (max-width: 748px) {
      position: absolute;
      right: 1rem;
      flex-direction: column;
      flex: 0.5;
      align-items: flex-end;

      &.hidden {
        display: none;
      }
      .link {
        margin: 2rem 1rem;
        animation: fade-in 0.3s ease forwards;
      }
    }
  }
}
</style>
