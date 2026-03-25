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

.hero {
  position: relative;
  min-height: 100vh;
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
  gap: 0.6rem;
}

.hero__logo {
  background-color: var(--black);
  width: 9.5rem;
  border-radius: 4.4rem;
  padding: 0.35rem;
}

.hero__title {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-transform: uppercase;
  font-weight: normal;
  gap: 0.1rem;
}

.hero__title-main {
  font-family: 'Bevan', sans-serif;
  font-size: clamp(1.8rem, 9vw, 4rem); 
  color: var(--yellow);
  letter-spacing: 0.2rem;
  line-height: 1;
}

.hero__title-sub {
  font-family: 'Oswald', sans-serif;
  font-size: clamp(0.8rem, 4vw, 1.5rem);
  color: var(--white);
  letter-spacing: 0.12rem;
  line-height: 1;
}

.hero__slogan-container {
  margin: 1.9rem 0;
  font-weight: lighter;
  display: flex;
  align-items: center;
  gap: 0.7rem;
}

.hero__line {
  height: 1px;
  width: clamp(2.7rem, 10vw, 5rem);
  background-color: var(--yellow);
}

.hero__slogan {
  font-family: 'Oswald', sans-serif;
  font-size: 1.25rem;
  font-size: clamp(0.8rem, 3.5vw, 1.25rem);
  color: var(--white);
  letter-spacing: 0.06rem;
  text-transform: uppercase;
}

.hero__icon {
  color: var(--yellow);
  font-size: 1.8rem;
  font-size: clamp(1.5rem, 3.6vw, 1.8rem);
  animation: bounce 1.5s ease-in-out infinite;
}

@media (max-width: 768px) {
  .hero {
    min-height: 100dvh;
    background: var(--black) url('../assets/images/hero.webp') 15% center/cover no-repeat;
  }
}
</style>
