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
    transform: translateY(8px);
  }
  100% {
    transform: translateY(0);
  }
}

.hero {
  position: relative;
  min-height: 768px;
  background: url('../assets/images/hero.webp') center/cover no-repeat;
}

.hero__overlay {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 10px;
}

.hero__logo {
  background-color: var(--black);
  width: 150px;
  border-radius: 70px;
  padding: 5px;
}

.hero__title {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-transform: uppercase;
  font-weight: normal;
  gap: 2px;
}

.hero__title-main {
  font-family: 'Bevan', sans-serif;
  font-size: 64px;
  color: var(--yellow);
  letter-spacing: 3px;
  line-height: 64px;
}

.hero__title-sub {
  font-family: 'Oswald', sans-serif;
  font-size: 24px;
  color: var(--white);
  letter-spacing: 2px;
  line-height: 24px;
}

.hero__slogan-container {
  margin: 30px 0;
  font-weight: lighter;
  display: flex;
  align-items: center;
  gap: 10px;
}

.hero__line {
  height: 1px;
  width: 75px;
  background-color: var(--yellow);
}

.hero__slogan {
  font-family: 'Oswald', sans-serif;
  font-size: 20px;
  color: var(--white);
  letter-spacing: 1px;
  text-transform: uppercase;
}

.hero__icon {
  color: var(--yellow);
  font-size: 30px;
  animation: bounce 1.5s ease-in-out infinite;
}
</style>
