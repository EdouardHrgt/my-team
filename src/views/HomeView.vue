<template>
  <div class="home">
    <NavBar />
    <!-- FIND THE BEST TALENT SECTION -->
    <section class="talent-wrapper">
      <div class="talent">
        <h1>
          Find the<br />
          best <strong>talent</strong>
        </h1>
        <div class="talent-txt">
          <p>
            Finding the right people and building high performing teams can be hard. Most companies
            aren’t tapping into the abundance of global talent. We’re about to change that.
          </p>
        </div>
      </div>
    </section>
    <!-- BUILD & MANAGE SECTION -->
    <section class="build-wrapper">
      <div class="build">
        <h2>Build & manage distributed teams like no one else.</h2>
        <ul>
          <li class="build-list" v-for="list in buildList" :key="list.index">
            <img :src="list.image" :alt="list.alt" />
            <div class="list-txt">
              <h3>{{ list.title }}</h3>
              <p>{{ list.text }}</p>
            </div>
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
  name: 'HomeView',
  components: {
    NavBar,
    FooterBar,
    HeroBar,
  },
  data() {
    return {
      buildList: [
        {
          index: '0',
          title: 'Experienced Individuals',
          image: require('../assets/icon-person.svg'),
          text: 'Our network is made up of highly experienced professionals who are passionate about what they do.',
          alt: 'icon of a person',
        },
        {
          index: '1',
          title: 'Easy to Implement',
          image: require('../assets/icon-cog.svg'),
          text: 'Our processes have been refined over years of implementation meaning our teams always deliver.',
          alt: 'icon of a cog',
        },
        {
          index: '2',
          title: 'Enhanced Productivity',
          image: require('../assets/icon-chart.svg'),
          text: 'Our customized platform with in-built analytics helps you manage your distributed teams.',
          alt: 'icon of a chart',
        },
      ],
    };
  },
};
</script>

<style scoped>
.home {
  min-height: 100vh;
  background-color: var(--clr-midnight-green);
}

/* FIND TALENT SECTION */
.talent-wrapper {
  width: 100%;
  padding-top: 2.5rem;
  background-image: url('../assets/bg-pattern-home-1.svg');
  background-repeat: no-repeat;
  background-position-y: 2rem;
  background-position-x: -6.25rem;
}

.talent {
  max-width: var(--max-width);
  margin: auto;
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  padding-bottom: 14rem;
  background-image: url('../assets/bg-pattern-home-2.svg');
  background-repeat: no-repeat;
  background-position: bottom right;
}

h1 {
  font-size: var(--h1-big-size);
  line-height: var(--h1-big-line);
  color: var(--clr-white);
}

h1 strong {
  color: var(--clr-light-coral);
}

.talent p {
  color: var(--clr-white);
  font-size: var(--body-1-size);
  line-height: var(--body-1-line);
  font-weight: 600;
  max-width: 27rem;
  position: relative;
}

.talent p::before {
  content: '';
  width: 50px;
  height: 4px;
  background-color: var(--clr-rapture-blue);
  position: absolute;
  top: -5.78rem;
}

/* BUILD AND MANAGE SECTION */
.build-wrapper {
  background-color: var(--clr-sacramento-state-green);
  background-image: url('../assets/bg-pattern-home-3.svg');
  background-repeat: no-repeat;
  background-position-y: bottom;
  background-position-x: calc(100% + 6.2rem);
}

.build {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  max-width: var(--max-width);
  margin: auto;
  padding: var(--home-padding) 0;
}

.build h2 {
  font-size: var(--h2-size);
  line-height: var(--h2-line);
  color: var(--clr-white);
  max-width: 32rem;
  position: relative;
  padding-top: 2rem;
}

.build h2::before {
  content: '';
  background-color: var(--clr-light-coral);
  height: 4px;
  width: 50px;
  position: absolute;
  top: -4px;
}

.build ul {
  border: 1px solid orange;
}

.build-list {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.list-txt h3 {
  color: var(--clr-light-coral);
  font-size: var(--h3-size);
  line-height: var(--h3-line);
  margin: 0 0 0.5rem 0;
}

.list-txt p {
  color: var(--clr-white);
  font-size: var(--body-2-size);
  line-height: var(--body-2-line);
  font-weight: 500;
  opacity: 0.8;
  max-width: 27.5rem;
}

@media screen and (max-width: 1700px) {
  .talent {
    border: none;
    max-width: 80%;
  }
  h1 {
    font-size: 90px;
  }
}

@media screen and (max-width: 1224px) {
  .talent {
    max-width: 90%;
  }
  .talent-wrapper {
    background-image: none;
  }
}

@media screen and (max-width: 1024px) {
  .talent {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-position: bottom center;
    padding-bottom: 16rem;
  }
  h1 {
    text-align: center;
  }
  .talent p {
    max-width: 35rem;
    padding: 1rem 0 0 0;
    text-align: center;
  }
  .talent p::before {
    display: none;
  }
}

@media screen and (max-width: 668px) {
  h1 {
    font-size: var(--h1-small-size);
    line-height: var(--h1-small-line);
  }
}
</style>
