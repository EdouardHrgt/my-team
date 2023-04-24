<template>
  <div class="home">
    <NavBar />
    <heroBar />
    <FooterBar />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import FooterBar from '@/components/FooterBar.vue';
import HeroBar from '@/components/HeroBar.vue'
export default {
  name: 'HomeView',
  components: {
    NavBar,
    FooterBar,
    HeroBar,
  },
};
</script>

<style scoped>
.home {
  min-height: 100vh;
  background-color: var(--clr-deep-jungle-green);
}
</style>
