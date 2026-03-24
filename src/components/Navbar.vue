<template>
  <nav class="navbar">
    <div class="navbar__header">
      <a href="#inicio" class="navbar__logo">
        <img class="navbar__image" :src="brasao" alt="Logo Bradadores MC">
        <h1 class="navbar__title">
          <span class="navbar__title-main">Bradadores</span>
          <span class="navbar__title-sub">Motoclube</span>
        </h1>
      </a>
      <button 
        class="navbar__toggle" 
        @click="menuOpen = !menuOpen"
        :class="{ active: menuOpen }"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>
    <ul class="navbar__menu" :class="{ active: menuOpen }">
      <li><a href="#inicio">Início</a></li>
      <li><a href="#sobre">Sobre</a></li>
      <li><a href="#localizacao">Onde estamos</a></li>
      <li><a href="#comando">Comando</a></li>
      <li><a href="#galeria">Galeria</a></li>
    </ul>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import brasao from '../assets/images/brasao.webp'

const menuOpen = ref(false)
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
  position: sticky;
  top: 0;
  z-index: 1000;
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

.navbar__toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 25px;
  height: 18px;
  background: none;
  border: none;
  cursor: pointer;
}

.navbar__toggle span {
  display: block;
  height: 3px;
  width: 100%;
  background-color: var(--white);
  border-radius: 2px;
  transition: all 0.3s ease;
}

.navbar__toggle.active span:nth-child(1) {
  transform: rotate(45deg) translate(5.5px, 5.5px);
}

.navbar__toggle.active span:nth-child(2) {
  opacity: 0;
}

.navbar__toggle.active span:nth-child(3) {
  transform: rotate(-45deg) translate(5.5px, -5.5px);
}

@media (max-width: 768px) {
  .navbar {
    flex-direction: column;
    padding: 10px 15px;
  }

  .navbar__header {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .navbar__menu {
    display: flex;
    flex-direction: column;
    gap: 10px;
    width: 100%;
    border-radius: 10px;
    font-size: 13px;
    opacity: 0;
    pointer-events: none;
    max-height: 0;
    transition: all 0.4s ease;
  }

  .navbar__menu.active {
    max-height: 300px;
    opacity: 1;
    padding-top: 15px;
    pointer-events: all;
    transition: all 0.8s ease;
  }

  .navbar__menu a {
    padding: 10px;
    border: 2px solid var(--white);
    border-radius: 10px;
    justify-content: center;
  }

  .navbar__menu a:hover {
    border: 2px solid var(--yellow);
  }

  .navbar__toggle {
    display: flex;
  }

  .navbar__toggle.active span {
    background-color: var(--yellow);
  }
}

</style>
