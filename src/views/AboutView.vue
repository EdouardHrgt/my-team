<template>
  <div class="about-page">
    <NavBar />
    <!-- ABOUT SECTION -->
    <section class="about-wrapper">
      <div class="about">
        <h1>About</h1>
        <p class="about-txt">
          We help companies build dynamic teams made up of top global talent. Using our network of
          passionate professionals we drive innovation and deliver incredible outcomes. Talented,
          diverse teams shape the best products and experiences. We’ll bring those teams to you.
        </p>
      </div>
    </section>
    <!-- CLIENTS SECTION -->
    <section class="clients-wrapper">
      <div class="clients">
        <h2>Some of our clients</h2>
        <ul>
          <li v-for="cli in clients" :key="cli.index" class="clients-list">
            <img :src="cli.logo" :alt="'logo of our client: ' + cli.name" tabIndex="0" />
          </li>
        </ul>
      </div>
    </section>
    <HeroBar />
    <FooterBar />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import FooterBar from '@/components/FooterBar.vue';
import HeroBar from '@/components/HeroBar.vue';
export default {
  components: {
    NavBar,
    FooterBar,
    HeroBar,
  },
  data() {
    return {
      clients: [
        { index: 0, logo: require('../assets/logo-the-verge.png'), name: 'the verge' },
        { index: 1, logo: require('../assets/logo-jakarta-post.png'), name: 'jakarta' },
        { index: 2, logo: require('../assets/logo-the-guardian.png'), name: 'the guardian' },
        { index: 3, logo: require('../assets/logo-tech-radar.png'), name: 'tech radar' },
        { index: 4, logo: require('../assets/logo-gadgets-now.png'), name: 'logo gadgets now' },
      ],
    };
  },
};
</script>

<style scoped>
h1 {
  font-size: var(--h1-small-size);
  line-height: var(--h1-small-line);
  color: var(--clr-white);
}

h2 {
  font-size: var(--h2-size);
  line-height: var(--h2-line);
  color: var(--clr-white);
}

h3 {
  font-size: var(--h3-size);
  line-height: var(--h3-line);
  font-weight: 600;
}

p {
  font-size: var(--body-1-size);
  line-height: var(--body-1-line);
  color: var(--clr-white);
  font-weight: 500;
}

/* MAIN SECTIONS  & commons props */
.about-wrapper {
  background-color: var(--clr-midnight-green);
  background-image: url('../assets/bg-pattern-about-1-mobile-nav-1.svg');
  background-repeat: no-repeat;
  background-position-x: calc(100% + 6.1rem);
  background-position-y: bottom;
}

.clients-wrapper {
  background-color: var(--clr-sacramento-state-green);
  background-repeat: no-repeat;
  background-image: url('../assets/bg-pattern-about-4.svg');
  background-position: top left;
}

.about,
.clients {
  padding: 6rem 0;
  max-width: var(--max-width);
  margin: auto;
}

/* ABOUT SECTION */
.about {
  display: flex;
  align-items: flex-start;
  gap: 12rem;
  padding-bottom: 9rem;
}

.about-txt {
  max-width: 44rem;
  position: relative;
}

.about-txt::before {
  content: '';
  width: 50px;
  height: 4px;
  background-color: var(--clr-light-coral);
  position: absolute;
  top: -2.25rem;
}

/* CLIENTS SECTION */
.clients {
  text-align: center;
}

.clients h2 {
  padding-top: 4.5rem;
}

.clients ul {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 5.5rem;
  padding: 3rem 0;
}

.clients-list {
  flex: 1;
}

@media screen and (max-width: 1440px) {
  .about,
  .clients {
    max-width: 90%;
  }
  .clients ul {
    gap: 4rem;
  }
  .about-txt {
    max-width: 37rem;
  }
}

@media screen and (max-width: 1133px) {
  .about-txt {
    max-width: 30rem;
    margin-bottom: 4rem;
  }
}

@media screen and (max-width: 1024px) {
  .clients ul {
    gap: 2.5rem;
  }
  .about {
    flex-direction: column;
    align-items: center;
    gap: 2.2rem;
  }
  .about-txt {
    max-width: 80%;
    margin-bottom: 5rem;
    text-align: center;
  }
  .about-txt::before {
    display: none;
  }
}

@media screen and (max-width: 668px) {
  .about-wrapper {
    background-position-x: calc(100% + 6.1rem);
    background-position-y: 23rem;
  }
  .clients-wrapper {
    background-position: unset;
    background-position-x: -6.3rem;
    background-position-y: -6.3rem;
  }
  .about,
  .clients {
    max-width: calc(100% - 3rem);
  }

  .about {
    padding-top: 0;
  }
  .about-txt {
    max-width: 90%;
    margin-bottom: 0;
  }
  h1 {
    font-size: 2.5rem;
  }
  h2 {
    font-size: 2rem;
  }
  .clients {
    padding-top: 1.5rem;
  }
  .clients ul {
    flex-direction: column;
    margin: auto;
    max-width: 60%;
  }
}
</style>
