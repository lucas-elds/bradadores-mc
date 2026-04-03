<template>
  <nav class="navbar">
    <div class="navbar__header">
      <a href="#inicio" class="navbar__logo">
        <img class="navbar__image" :src="logo" alt="Logo Bradadores MC">
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
      <li><a href="#inicio" :class="{ active: activeSection === 'inicio' }">Início</a></li>
      <li><a href="#sobre" :class="{ active: activeSection === 'sobre' }">Sobre</a></li>
      <li><a href="#localizacao" :class="{ active: activeSection === 'localizacao' }">Onde estamos</a></li>
      <li><a href="#comando" :class="{ active: activeSection === 'comando' }">Comando</a></li>
      <li><a href="#galeria" :class="{ active: activeSection === 'galeria' }">Galeria</a></li>
      <li><a href="#galeria" :class="{ active: activeSection === 'contato' }">Contato</a></li>
    </ul>
  </nav>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import logo from '../assets/images/logo.webp'

const menuOpen = ref(false)

const activeSection = ref('inicio')

onMounted(() => {
  const watcher = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        const id = entry.target.id
        activeSection.value = id
        history.replaceState(null, null, `#${id}`)
      }
    })
  }, { 
    threshold: 0.6 
  })
  document.querySelectorAll('section[id]').forEach((section) => {
    watcher.observe(section)
  })
})
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.6rem clamp(1rem, 2vw, 2.2rem);
  background-color: var(--black);
  text-transform: uppercase;
  border-bottom: 1px solid var(--yellow);
  position: sticky;
  top: 0;
  z-index: 1000;
  height: var(--nav-height);
}

.navbar__logo {
  display: flex;
  align-items: center;
  gap: 0.4rem;
}

.navbar__image {
  height: 3rem;
}

.navbar__title {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  letter-spacing: 0.05rem;
  font-weight: normal;
  line-height: 1;
  gap: 0.2rem;
}

.navbar__title-main {
  font-family: 'Alfa Slab One', serif;
  font-size: 0.9rem;
  color: var(--yellow);
}

.navbar__title-sub {
  font-family: 'Oswald', sans-serif;
  font-size: 0.8rem;
  color: var(--white);
}

.navbar__menu {
  font-family: 'Roboto', sans-serif;
  font-weight: bold;
  font-size: clamp(0.8rem, 0.8vw, 0.85rem);
  display: flex;
  gap: clamp(1rem, 3vw, 2.2rem);
}

.navbar__menu a {
  display: flex;
  color: var(--white);
  transition: all 0.3s ease;
  padding: 0.1rem 0;
  border-bottom: 0.1rem solid var(--black);
}

.navbar__menu a.active {
  color: var(--yellow);
  border-bottom: 0.1rem solid var(--yellow);
}

.navbar__menu a:hover {
  color: var(--yellow);
}

.navbar__toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 1.5rem;
  height: 1.1rem;
  background: none;
  border: none;
  cursor: pointer;
}

.navbar__toggle span {
  display: block;
  height: 0.2rem;
  width: 100%;
  background-color: var(--white);
  border-radius: 0.1rem;
  transition: all 0.3s ease;
}

.navbar__toggle.active span:nth-child(1) {
  transform: rotate(45deg) translate(0.33rem, 0.33rem);
}

.navbar__toggle.active span:nth-child(2) {
  opacity: 0;
}

.navbar__toggle.active span:nth-child(3) {
  transform: rotate(-45deg) translate(0.33rem, -0.33rem);
}

@media (max-width: 768px) {
  .navbar {
    justify-content: center;
    flex-direction: column;
  }

  .navbar__image {
    height: 2.7rem;
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
    gap: 0.6rem;
    width: 100%;
    opacity: 0;
    pointer-events: none;
    transition: all 0.4s ease;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: var(--black);
    border-bottom: 1px solid var(--yellow);
    padding: 1rem;
  }

  .navbar__menu.active {
    opacity: 1;
    pointer-events: all;
    transition: all 0.8s ease;
  }

  .navbar__menu a {
    padding: 1.2vmin;
    border: 2px solid var(--white);
    border-radius: 0.6rem;
    justify-content: center;
  }

  .navbar__menu a.active {
    border: 2px solid var(--yellow);
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
