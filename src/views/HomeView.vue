<template>
  <div class="home">
    <NavBar />
    <FooterBar />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import FooterBar from '@/components/FooterBar.vue';
export default {
  name: 'HomeView',
  components: {
    NavBar,
    FooterBar,
  },
};
</script>

<style scoped>
.home {
  min-height: 100vh;
  background-color: var(--clr-deep-jungle-green);
}
</style>
