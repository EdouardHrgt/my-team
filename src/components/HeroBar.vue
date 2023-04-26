<template>
  <div class="hero">
    <section class="hero-bar">
      <div class="hero-content">
        <h2>Ready to get started?</h2>
        <button><router-link :to="{ name: 'contact' }">contact us</router-link></button>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'HeroBar',
};
</script>

<style scoped>
.hero-bar {
  background-color: var(--clr-light-coral);
  padding: 4.688rem 0;
  background-image: url('../assets/bg-pattern-home-6-about-5.svg');
  background-repeat: no-repeat;
  background-position: bottom 0 left 0;
}

.hero-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 917px;
  margin: auto;
}

h2 {
  color: var(--clr-dark-green);
  font-size: var(--h2-size);
  font-weight: 700;
  line-height: var(--h2-line);
}

button {
  background-color: transparent;
  border: 2px solid var(--clr-dark-green);
  border-radius: 50px;
  padding: 0.657rem 1.988rem;
  cursor: pointer;
}

button:hover {
  background-color: var(--clr-dark-green);
}

button:hover a {
  color: var(--clr-white);
}

button a {
  color: var(--clr-dark-green);
  font-weight: 500;
  font-size: var(--body-1-size);
  transition: color 0.2s ease-in-out;
}

@media screen and (max-width: 1250px) {
  .hero-content {
    max-width: 720px;
    padding: 0;
  }
}

@media screen and (max-width: 1024px) {
  .hero-content {
    max-width: 700px;
  }
  h2 {
    color: var(--clr-dark-green);
    font-size: 2rem;
  }
}

@media screen and (max-width: 768px) {
  .hero-content {
    flex-direction: column;
  }
  button {
    margin-top: 2rem;
    margin-bottom: 2rem;
  }
}

@media screen and (max-width: 668px) {
  .hero-content {
    padding: 0 1.5rem;
  }
}
</style>
