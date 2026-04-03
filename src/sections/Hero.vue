<template>
  <section class="hero">
    <div class="hero__overlay">
      <img class="hero__logo" :src="logo" alt="Logo Bradadores MC">
      
      <h1 class="hero__title">
        <span class="hero__title-main">Bradadores</span>
        <span class="hero__title-sub">Motoclube</span>
      </h1>

      <h2 class="hero__slogan-container">
        <span class="hero__line"></span>
        <span class="hero__slogan">Respeito, Honra e Lealdade</span>
        <span class="hero__line"></span>
      </h2>

      <a class="hero__icon" href="#sobre"><i class="fa-solid fa-chevron-down"></i></a>
    </div>
  </section>
</template>

<script setup>
import logo from '../assets/images/logo.webp'
</script>

<style scoped>

@keyframes bounce {
  0% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(0.5rem);
  }
  100% {
    transform: translateY(0);
  }
}

@keyframes drop {
  from {
    opacity: 0;
    transform: translateY(-20vmin);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero {
  position: relative;
  min-height: var(--section-height);
  background: var(--black) url('../assets/images/hero.webp') center/cover no-repeat;
}

.hero__overlay {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: clamp(0.2rem, 1vmin, 2.5rem);
}

.hero__logo {
  width: clamp(1rem, 30vmin, 25rem);
  animation: drop 1s ease-out;
}

.hero__title {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-transform: uppercase;
  font-weight: normal;
  line-height: 1;
  animation: drop 1s ease-out;
}

.hero__title-main {
  font-family: 'Alfa Slab One', serif;
  font-size: clamp(1rem, 11vmin, 9rem);
  color: var(--yellow);
  letter-spacing: 0.4vmin;
}

.hero__title-sub {
  font-family: 'Oswald', sans-serif;
  font-size: clamp(1rem, 5vmin, 4rem);
  color: var(--white);
  letter-spacing: 0.2vmin;
}

.hero__slogan-container {
  margin: clamp(1rem, 3vmin, 2.5rem);
  font-weight: lighter;
  display: flex;
  align-items: center;
  gap: clamp(1rem, 2vmin, 3rem);
  animation: drop 1s ease-out;
}

.hero__line {
  height: 1px;
  width: clamp(1rem, 10vmin, 8rem);
  background-color: var(--yellow);
}

.hero__slogan {
  font-family: 'Oswald', sans-serif;
  font-size: clamp(1rem, 3.3vmin, 2.8rem);
  color: var(--white);
  letter-spacing: 0.1vmin;
  text-transform: uppercase;
}

.hero__icon {
  color: var(--yellow);
  font-size: clamp(1rem, 4vmin, 3rem);
  animation: bounce 1.5s ease-in-out infinite;
}

@media (max-width: 768px) {
  .hero {
    background: var(--black) url('../assets/images/hero.webp') 15% center/cover no-repeat;
  }
}
</style>
