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

</template>

<style scoped>
  .navbar-expand-lg .navbar-collapse{
    background-color: aliceblue;
  }

  .container, .container-lg, .container-md, .container-sm, .container-xl, .container-xxl{
    background-color: aliceblue;
  }

</style>
