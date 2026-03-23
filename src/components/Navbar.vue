<template>
  <nav class="navbar">
    <a href="#inicio" class="navbar__logo">
      <img class="navbar__image" :src="brasao" alt="Logo Bradadores MC">
      <h1 class="navbar__title">
        <span class="navbar__title-main">Bradadores</span>
        <span class="navbar__title-sub">Motoclube</span>
      </h1>
    </a>
    <ul class="navbar__menu">
      <li><a href="#inicio">Início</a></li>
      <li><a href="#sobre">Sobre</a></li>
      <li><a href="#localizacao">Onde estamos</a></li>
      <li><a href="#comando">Comando</a></li>
      <li><a href="#galeria">Galeria</a></li>
    </ul>
  </nav>
</template>

<script setup>
import brasao from '../assets/images/brasao.webp'
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 40px;
  background-color: var(--black);
  text-transform: uppercase;
  border-bottom: 1px solid var(--yellow);
}

.navbar__logo {
  display: flex;
  align-items: center;
  gap: 10px;
}

.navbar__image {
  height: 60px;
}

.navbar__title {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  letter-spacing: 1.5px;
  font-weight: normal;
}

.navbar__title-main {
  font-family: 'Bevan', sans-serif;
  font-size: 14px;
  color: var(--yellow);
}

.navbar__title-sub {
  font-family: 'Oswald', sans-serif;
  font-size: 13px;
  color: var(--white);
}

.navbar__menu {
  font-family: 'Roboto', sans-serif;
  font-weight: bold;
  font-size: 14px;
  display: flex;
  gap: 40px;
}

.navbar__menu a {
  display: flex;
  color: var(--white);
  transition: all 0.3s ease;
  padding: 2px 0;
  border-bottom: 2px solid var(--black);
}

.navbar__menu a:hover {
  color: var(--yellow);
  border-bottom: 2px solid var(--yellow);
}

</style>
