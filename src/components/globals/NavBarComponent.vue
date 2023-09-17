<script setup>

</script>

<template>
  <div class="container">
    <nav class="navbar navbar-expand-lg mt-0">
      <a class="btn">Accueil</a>

      <a class="btn">A Propos</a>

      <a class="btn">Contact</a>
    </nav>
  </div>
</template>
  
<style scoped>
nav {
  position: fixed;
  top: 0;
  width: 80%;
  z-index: 1;
  display: flex;
  align-items: center;
  padding: 20px;
  background: #0d1523;
}

nav a {
  color: #81c0ee;
  text-decoration: none;
  /* margin-left: 20px; */
}

nav a.a-active {
  color: #fff;
}
</style>