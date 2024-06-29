<script setup>
import { RouterLink, RouterView } from 'vue-router'   
</script>

<template>
  <aside class="header-vertical">
    <div class="nav-bar">
      <h1>LOGO</h1>
      <nav class="nav">
        <RouterLink to="/">Incio</RouterLink>
        <RouterLink to="/about">Carrito</RouterLink>
      </nav>
    </div>
  </aside>

  <RouterView />
</template>

<style scoped>

@media (min-width: 1024px) {
  .header-vertical{
    position: sticky;
    top: 0px;
    min-height: 100vh;
    background: aqua;
  }

  .nav-bar{
    background: red;
    text-align: center;
    padding: 10px 0px;
  }

  .nav{
    background: pink;
    display: flex;
    flex-direction: column;
    padding: 20px;
  }
}
  

</style>
