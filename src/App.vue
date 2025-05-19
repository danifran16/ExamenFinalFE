<script>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
</script>

<template>

  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <router-link class="nav-link" to="/">Ejercicio 1</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/Ejercicio2">Ejercicio 2</router-link>
        </li>
      </ul>
  </div>
</nav>

<div class="container py-4">


      <router-view />
    </div>
  <!-- <router-view /> -->


</template>

<style scoped>
/* header {
  line-height: 1.5;
}
 */
/* .logo {
  display: block;
  margin: 0 auto 2rem;
} */

/* @media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  } */

/*   .logo {
    margin: 0 2rem 0 0;
  } */

/*   header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  } */
/* } */
</style>
