<template>
  <div class="about">
    <NavBar />
    <h1>This is an about page</h1>
    <FooterBar />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import FooterBar from '@/components/FooterBar.vue';
export default {
  components: {
    NavBar,
    FooterBar,
  },
};
</script>
