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

    <!-- DIRECTORS SECTION -->
    <section class="directors-wrapper">
      <div class="directors">
        <h2>Meet the directors</h2>
        <div class="directors-grid">
          <div class="director" v-for="(director, i) in directors" :key="i" :ref="director.name">
            <div class="director-filter" v-if="isOpen == i"></div>
            <div
              class="director-ball"
              @click="toggleDirector(i)"
              tabIndex="0"
              :aria-label="'Open the profile of: ' + director.name"
            >
              <img
                :class="{ activeBall: isOpen == i }"
                src="../assets/icon-cross.svg"
                alt="toggle the director's infos"
              />
            </div>

            <div class="director-default">
              <img v-if="isOpen != i" :src="director.img" :alt="'picture of ' + director.name" />
              <p>
                <strong>{{ director.name }}</strong>
              </p>
              <p class="director-position" v-if="isOpen != i">{{ director.position }}</p>
            </div>
            <div class="director-hover" v-if="isOpen == i">
              <p class="director-quote">{{ director.quote }}</p>
              <ul class="director-links">
                <li>
                  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="20">
                    <path
                      d="M24 2.557a9.83 9.83 0 01-2.828.775A4.932 4.932 0 0023.337.608a9.864 9.864 0 01-3.127 1.195A4.916 4.916 0 0016.616.248c-3.179 0-5.515 2.966-4.797 6.045A13.978 13.978 0 011.671 1.149a4.93 4.93 0 001.523 6.574 4.903 4.903 0 01-2.229-.616c-.054 2.281 1.581 4.415 3.949 4.89a4.935 4.935 0 01-2.224.084 4.928 4.928 0 004.6 3.419A9.9 9.9 0 010 17.54a13.94 13.94 0 007.548 2.212c9.142 0 14.307-7.721 13.995-14.646A10.025 10.025 0 0024 2.557z"
                    />
                  </svg>
                </li>
                <li>
                  <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20">
                    <path
                      d="M18 0H2C.9 0 0 .9 0 2v16c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V2c0-1.1-.9-2-2-2zM6 17H3V8h3v9zM4.5 6.3c-1 0-1.8-.8-1.8-1.8s.8-1.8 1.8-1.8 1.8.8 1.8 1.8-.8 1.8-1.8 1.8zM17 17h-3v-5.3c0-.8-.7-1.5-1.5-1.5s-1.5.7-1.5 1.5V17H8V8h3v1.2c.5-.8 1.6-1.4 2.5-1.4 1.9 0 3.5 1.6 3.5 3.5V17z"
                    />
                  </svg>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CLIENTS SECTION -->
    <section class="clients-wrapper">
      <div class="clients">
        <h2>Some of our clients</h2>
        <ul>
          <li v-for="cli in clients" :key="cli.index" class="clients-list">
            <img :src="cli.logo" :alt="'logo of our client: ' + cli.name" tabIndex="0"  :aria-label="'logo of our client: ' + cli.name"/>
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
  methods: {
    toggleDirector(idx) {
      console.warn(idx);
      this.isOpen == idx ? (this.isOpen = -1) : (this.isOpen = idx);
    },
  },
  data() {
    return {
      isOpen: -1,
      clients: [
        { index: 0, logo: require('../assets/logo-the-verge.png'), name: 'the verge' },
        { index: 1, logo: require('../assets/logo-jakarta-post.png'), name: 'jakarta' },
        { index: 2, logo: require('../assets/logo-the-guardian.png'), name: 'the guardian' },
        { index: 3, logo: require('../assets/logo-tech-radar.png'), name: 'tech radar' },
        { index: 4, logo: require('../assets/logo-gadgets-now.png'), name: 'logo gadgets now' },
      ],
      directors: [
        {
          name: 'Nikita Marks',
          position: 'Founder & CEO',
          img: require('../assets/avatar-nikita.jpg'),
          quote: '“It always amazes me how much talent there is in every corner of the globe.”',
        },
        {
          name: 'Cristian Duncan',
          position: 'Co-founder & COO',
          img: require('../assets/avatar-christian.jpg'),
          quote:
            '“Distributed teams required unique processes. You need to approach work in a new way.”',
        },
        {
          name: 'Cruz Hamer',
          position: 'Co-founder & CTO',
          img: require('../assets/avatar-cruz.jpg'),
          quote:
            "“Technology is at the forefront of enabling distributed teams. That's where we come in.”",
        },
        {
          name: 'Drake Heaton',
          position: 'Business Development Lead',
          img: require('../assets/avatar-drake.jpg'),
          quote:
            '“Hiring similar people from similar backgrounds is a surefire way to stunt innovation.”',
        },
        {
          name: 'Griffin Wise',
          position: 'Lead Marketing',
          img: require('../assets/avatar-griffin.jpg'),
          quote:
            '“Unique perspectives shape unique products, which is what you need to survive these days.”',
        },
        {
          name: 'Aden Allan',
          position: 'Head of Talent',
          img: require('../assets/avatar-aden.jpg'),
          quote:
            '“Empowered teams create truly amazing products. Set the north star and let them follow it.”',
        },
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

.directors-wrapper {
  background-color: var(--clr-deep-jungle-green);
  background-repeat: no-repeat;
  background-image: url('../assets/bg-pattern-about-2-contact-1.svg');
  background-position-x: -6.2rem;
  background-position-y: top;
}

.clients-wrapper {
  background-color: var(--clr-sacramento-state-green);
  background-repeat: no-repeat;
  background-image: url('../assets/bg-pattern-about-4.svg');
  background-position: top left;
}

.about,
.clients,
.directors {
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

/* DIRECTORS SECTION */
.directors h2 {
  text-align: center;
}

.directors-grid {
  padding: 4rem 0;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(2, 1fr);
  grid-column-gap: 3rem;
  grid-row-gap: 5rem;
}

.director {
  background-color: var(--clr-sacramento-state-green);
  position: relative;
  min-width: 350px;
  height: 253px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  isolation: isolate;
}

.director-filter {
  position: absolute;
  inset: 0;
  background-color: var(--clr-dark-green);
  z-index: -1;
}

.director-hover svg {
  fill: var(--clr-white);
  cursor: pointer;
  transition: 0.3s;
}

.director-hover svg:hover {
  fill: var(--clr-light-coral);
}

.director-ball {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background-color: var(--clr-light-coral);
  position: absolute;
  bottom: -28px;
  left: 50%;
  transform: translate(-50%, 0);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}

.director-ball img {
  transition: 0.2s ease-in-out;
}

.activeBall {
  transform: rotate(45deg);
}

.director p {
  text-align: center;
}

.director p strong {
  font-size: var(--body-1-size);
  line-height: var(--body-1-line);
  color: var(--clr-rapture-blue);
}

.director-position,
.director-quote {
  font-size: var(--body-2-size);
  line-height: var(--body-2-line);
}

.director-position {
  font-style: italic;
}

.director-quote {
  max-width: 16rem;
  margin: 1rem auto 0;
}

.director-default img {
  width: 96px;
  height: 96px;
  border: 2px solid var(--clr-rapture-blue);
  border-radius: 50%;
  margin: 0 auto 1rem;
}

.director-links {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1.5rem;
  margin: 1rem 0;
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
  .clients,
  .directors {
    max-width: 90%;
  }
  .clients ul {
    gap: 4rem;
  }
  .about-txt {
    max-width: 37rem;
  }
}

@media screen and (max-width: 1280px) {
  .directors-grid {
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(auto, 1fr);
    grid-column-gap: 3%;
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
  .directors-grid {
    grid-column-gap: 1rem;
  }
}

@media screen and (max-width: 800px) {
  .directors-grid {
    grid-template-columns: repeat(1, 1fr);
    grid-template-rows: repeat(auto, 1fr);
    grid-row-gap: 4rem;
  }
  .director {
    width: 90%;
    min-width: unset;
    margin: auto;
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
  .directors-wrapper {
    background-position-x: -6.2rem;
    background-position-y: -6.3rem;
  }
  .about,
  .clients,
  .directors {
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
  .director {
    width: 100%;
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
