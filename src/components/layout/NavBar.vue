<script setup>
import { ref } from 'vue';

/*
  Mobile app nav
*/
const showMobileNav = ref(false)

</script>

<template>
  <nav
    aria-label="main navigation"
    class="navbar is-danger"
    role="navigation"
  >
  <div class="container is-max-desktop px-2">
    <div class="navbar-brand">
    <div class="navbar-item is-size-4 is-family-monospace">
      NoteTaking App
    </div>

    <a
      aria-expanded="false"
      aria-label="menu"
      class="navbar-burger"
      :class="{ 'is-active' : showMobileNav }"
      data-target="navbarBasicExample"
      role="button"
      @click.prevent="showMobileNav = !showMobileNav"
    >
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </a>
  </div>

 <div
    :class="{ 'is-active' : showMobileNav }"
    class="navbar-menu"
    id="navbarBasicExample"
    @click.prevent="showMobileNav = !showMobileNav"
  >
    <div class="navbar-start">
      
    </div>

    <div class="navbar-end">
      <RouterLink
        class="navbar-item"
        to="/"
        active-class="is-active"
      >
        Notes
      </RouterLink>
      <RouterLink
        class="navbar-item"
        to="/stats"
        active-class="is-active"
      >
        Stats
      </RouterLink>
     
    </div>
  </div>
  </div>
</nav>
</template>


<style scoped>
  @media (max-width: 1023px) {
    .navbar-menu {
      position: absolute;
      left: 0;
      width: 100%;
    }
  }
</style>