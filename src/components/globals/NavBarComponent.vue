<script setup>

</script>

<template>
    <nav class="navbar navbar-expand-lg mt-0">
      <a class="btn">Accueil</a>
      
      <a class="btn">A Propos</a>
      
      <a class="btn">Contact</a>
    </nav>
  </template>
  
  <style scoped>
  nav {
    display: flex;
    align-items: center;
    padding: 20px;
    background: #333;
  }
  
  nav a {
    color: #fff;
    text-decoration: none;
    margin-left: 20px;
  }
  
  nav a.a-active {
    color: blue;
  }
  </style>