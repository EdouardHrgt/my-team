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
    <!-- DELIVERING SECTION -->
    <div class="delivery-wrapper">
      <div class="delivery">
        <h2>
          Delivering real results for top <br />
          companies. Some of our <strong>success stories.</strong>
        </h2>
        <ul class="delivery-list">
          <li v-for="quote in deliveryList" :key="quote.index">
            <div class="delivery-list-txt">
              <p>{{ quote.txt }}</p>
              <h3>{{ quote.author }}</h3>
              <aside>{{ quote.role }}</aside>
              <img :src="quote.img" :alt="'picture of ' + quote.author" />
            </div>
          </li>
        </ul>
      </div>
    </div>
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
      deliveryList: [
        {
          index: '0',
          txt: '“The team perfectly fit the specialized skill set required. They focused on the most essential features helping us launch the platform eight months faster than planned.”',
          author: 'Kady Baker',
          role: 'Product Manager at Bookmark',
          img: require('../assets/avatar-kady.jpg'),
        },
        {
          index: '1',
          txt: '“We needed to automate our entire onboarding process. The team came in and built out the whole journey. Since going live, user retention has gone through the roof!”',
          author: 'Aiysha Reese',
          role: 'Founder of Manage',
          img: require('../assets/avatar-aiysha.jpg'),
        },
        {
          index: '2',
          txt: '“Amazing. Our team helped us build an app that delivered a new experience for hiring a physio. The launch was an instant success with 100k downloads in the first month.”',
          author: 'Arthur Clarke',
          role: 'Co-founder of MyPhysio',
          img: require('../assets/avatar-arthur.jpg'),
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

h1 strong {
  color: var(--clr-light-coral);
}

.list-txt,
.delivery-list p {
  color: var(--clr-white);
  font-size: var(--body-2-size);
  line-height: var(--body-2-line);
  font-weight: 500;
  opacity: 0.9;
}

aside {
  color: var(--clr-white);
  font-size: var(--body-2-size);
  line-height: var(--body-2-line);
  font-style: italic;
  font-weight: 400;
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

.build-list {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.list-txt h3 {
  color: var(--clr-light-coral);
  margin: 0 0 0.5rem 0;
}

.list-txt p {
  max-width: 27.5rem;
}

/* Delivering SECTION */
.delivery-wrapper {
  background-image: url('../assets/bg-pattern-home-4-about-3.svg'),
    url('../assets/bg-pattern-home-5.svg');
  background-repeat: no-repeat;
  background-position: top left, bottom right;
}

.delivery {
  padding: var(--home-padding) 0;
  max-width: var(--max-width);
  margin: auto;
}

.delivery h2 {
  text-align: center;
}

.delivery h2 strong {
  color: var(--clr-rapture-blue);
}

.delivery-list {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 3.5rem auto 0;
}

.delivery-list-txt {
  padding-top: 2.3rem;
  max-width: 22rem;
  text-align: center;
  background-image: url('../assets/icon-quotes.svg');
  background-repeat: no-repeat;
  background-position: center top;
}

.delivery-list h3 {
  color: var(--clr-rapture-blue);
  margin: 1rem 0 0 0;
}

.delivery-list li img {
  width: 62px;
  height: 62px;
  border: 2px solid var(--clr-rapture-blue);
  border-radius: 50%;
  margin: 1rem auto 0;
}

@media screen and (max-width: 1700px) {
  .talent,
  .build,
  .delivery {
    max-width: 80%;
  }
  .build {
    gap: 1rem;
  }
  h1 {
    font-size: 90px;
  }
  .delivery-list {
    gap: 4rem;
  }
}

@media screen and (max-width: 1224px) {
  .talent,
  .build,
  .delivery {
    max-width: 90%;
  }
  .talent-wrapper {
    background-image: none;
  }
  .build-wrapper {
    background-size: 170px;
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
  .build h2,
  .delivery h2 {
    font-size: 2rem;
    line-height: 2.2rem;
  }
  .talent p {
    max-width: 35rem;
    padding: 1rem 0 0 0;
    text-align: center;
  }
  .talent p::before {
    display: none;
  }
  .build-wrapper {
    background-position-y: top;
    background-size: initial;
  }
  .build {
    flex-direction: column;
    align-items: center;
    justify-content: center;
    max-width: 90%;
    gap: 3rem;
  }
  .delivery-list {
    flex-direction: column;
  }
  .delivery-list-txt {
    max-width: 34rem;
  }
}

@media screen and (max-width: 668px) {
  h1 {
    font-size: var(--h1-small-size);
    line-height: var(--h1-small-line);
  }
  .build h2 {
    max-width: 15rem;
    align-self: flex-start;
  }
}

@media screen and (max-width: 500px) {
  .delivery h2,
  .build h2 {
    font-size: 1.5rem;
  }
}
</style>
