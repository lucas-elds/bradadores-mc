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
  min-height: 768px;
  height: calc(100vh - var(--nav-height));
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
  gap: clamp(0.6rem, 0.4vw + 0.8vh, 1rem);
}

.hero__logo {
  width: clamp(15rem, 8vw + 10vh, 17rem);
}

.hero__title {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-transform: uppercase;
  font-weight: normal;
}

.hero__title-main {
  font-family: 'Bevan', sans-serif;
  font-size: clamp(4rem, 2.5vw + 4vh, 5rem);
  color: var(--yellow);
  letter-spacing: 0.15rem;
  line-height: 1;
}

.hero__title-sub {
  font-family: 'Oswald', sans-serif;
  font-size: clamp(1.8rem, 0.8vw + 1.3vh, 2rem);
  color: var(--white);
  letter-spacing: 0.08rem;
  line-height: 1;
}

.hero__slogan-container {
  margin: clamp(1.5rem, 0.8vw + 1vh, 2rem);
  font-weight: lighter;
  display: flex;
  align-items: center;
  gap: 0.7rem;
}

.hero__line {
  height: 1px;
  width: clamp(5rem, 3vw + 5vh, 6rem);
  background-color: var(--yellow);
}

.hero__slogan {
  font-family: 'Oswald', sans-serif;
  font-size: clamp(0.8rem, 0.8vw + 1vh, 1.5rem);
  color: var(--white);
  letter-spacing: 0.05rem;
  text-transform: uppercase;
}

.hero__icon {
  color: var(--yellow);
  font-size: clamp(1.5rem, 3.6vw, 1.8rem);
  animation: bounce 1.5s ease-in-out infinite;
}

@media (max-width: 768px) {
  .hero {
    height: calc(100dvh - var(--nav-height));
    background: var(--black) url('../assets/images/hero.webp') 15% center/cover no-repeat;
  }

  .hero__logo {
    width: 35vw;
  }

  .hero__title-main {
    font-size: 10vw;
  }

  .hero__title-sub {
    font-size: 4vw;
  }

  .hero__line {
    width: 4vh;
  }

  .hero__slogan {
    font-size: 3vw;
  }

  .hero__slogan-container {
    margin: 5vh;
  }
}
</style>
