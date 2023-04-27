<template>
  <div>
    <div class="contact-page">
      <NavBar />
      <section class="contact-wrapper">
        <div class="contact">
          <div class="contact-infos">
            <h1>Contact</h1>
            <h2 @click="resetErrors">Ask us about</h2>
            <ul>
              <li v-for="el in list" :key="el.index">
                <img :src="el.icon" :alt="'icon of ' + el.alt" />
                <p class="list-txt">{{ el.txt }}</p>
              </li>
            </ul>
          </div>
          <div class="contact-form">
            <form @submit.prevent="sendForm()" novalidate>
              <!-- Name input -->
              <div class="form-group">
                <label for="name" hidden>Name:</label>
                <input type="text" name="name" id="name" placeholder="Name" v-model="name" />
                <p class="error" v-show="errors.name">{{ errors.name }}</p>
              </div>
              <!-- Email input -->
              <div class="form-group">
                <label for="email" hidden>Email:</label>
                <input type="email" name="email" id="email" placeholder="Email" v-model="email" />
                <p class="error" v-show="errors.email">{{ errors.email }}</p>
              </div>
              <!-- Company input -->
              <div class="form-group">
                <label for="company" hidden>Company:</label>
                <input
                  type="text"
                  name="company"
                  id="company"
                  placeholder="Company Name"
                  v-model="company"
                />
                <p class="error" v-show="errors.company">{{ errors.company }}</p>
              </div>
              <!-- Title input -->
              <div class="form-group">
                <label for="title" hidden>Title:</label>
                <input type="text" name="title" id="title" placeholder="Title" v-model="title" />
                <p class="error" v-show="errors.title">{{ errors.title }}</p>
              </div>
              <!-- message input -->
              <div class="form-group">
                <label for="message" hidden>Message:</label>
                <input
                  type="text"
                  name="message"
                  id="message"
                  placeholder="Message"
                  v-model="message"
                />
                <p class="error" v-show="errors.message">{{ errors.message }}</p>
              </div>
              <!-- Submit form button -->
              <input type="submit" value="submit" class="submit-btn" />
            </form>
          </div>
        </div>
      </section>
      <FooterBar />
    </div>
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
  data() {
    return {
      name: '',
      email: '',
      company: '',
      title: '',
      message: '',
      errors: {
        name: '',
        email: '',
        title: '',
        message: '',
        company: '',
      },
      list: [
        {
          index: 0,
          icon: require('../assets/icon-person.svg'),
          txt: 'The quality of our talent network',
          alt: 'a worker',
        },
        {
          index: 1,
          icon: require('../assets/icon-cog.svg'),
          txt: 'Usage & implementation of our software',
          alt: 'a cog',
        },
        {
          index: 2,
          icon: require('../assets/icon-chart.svg'),
          txt: 'How we help drive innovation',
          alt: 'a chart',
        },
      ],
    };
  },
  methods: {
    sendForm() {
      this.resetErrors();
      const myForm = [this.name, this.email, this.company, this.title, this.message];
      if (this.name && this.email && this.company && this.title && this.message) {
        alert('form sent');
      } else {
        myForm.forEach((input, i) => {
          if (!input) {
            if (i == 0) {
              this.errors.name = 'name required';
            }
            if (i == 1) {
              this.errors.email = 'email required';
            }
            if (i == 2) {
              this.errors.company = 'compagny name required';
            }
            if (i == 3) {
              this.errors.title = 'title required';
            }
            if (i == 4) {
              this.errors.message = 'message required';
            }
          }
        });
      }
    },
    resetErrors() {
      this.errors = {
        name: '',
        email: '',
        title: '',
        message: '',
        company: '',
      };
    },
  },
};
</script>

<style scoped>
.contact-page {
  min-height: 100vh;
  background-color: rgb(253, 228, 71);
}

.contact-wrapper {
  background-color: var(--clr-midnight-green);
  background-image: url('../assets/bg-pattern-about-2-contact-1.svg'),
    url('../assets/bg-pattern-contact-2.svg');
  background-repeat: no-repeat;
  background-position-x: -6.2rem, calc(100% + 6.2rem);
  background-position-y: 0, bottom;
}

.contact {
  max-width: var(--max-width);
  margin: auto;
  display: flex;
  justify-content: space-between;
  padding: 1rem 0 8rem 0;
  gap: 2rem;
}

h1 {
  font-size: var(--h1-small-size);
  line-height: 6.25rem;
  color: var(--clr-white);
}

h2 {
  font-size: 2rem;
  line-height: 3rem;
  color: var(--clr-light-coral);
}

li p {
  color: var(--clr-white);
  font-size: var(--body-1-size);
  line-height: var(--body-1-line);
  font-weight: 500;
}

li {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin: 1rem 0;
}

/* THE FORM */
form {
  width: 540px;
}

input {
  background: transparent;
  border: none;
  border-bottom: 1px solid var(--clr-transp-white);
  padding: 1rem 0 1rem 1rem;
  margin: 0.5rem 0;
  width: 100%;
  color: var(--clr-white);
  font-size: var(--body-1-size);
}

input:focus {
  border: none;
  outline: none;
  border-bottom: 1px solid var(--clr-transp-white);
}

input[type='submit'] {
  width: unset;
  border: none;
  color: var(--clr-dark-green);
  font-weight: 600;
  font-size: var(--body-1-size);
  background-color: var(--clr-white);
  padding: 0.7rem 2.01rem;
  border-radius: 50px;
  cursor: pointer;
  transition: 0.3s ease-in-out;
  margin-top: 1.2rem;
}

input[type='submit']:hover {
  background-color: var(--clr-rapture-blue);
}

input::placeholder {
  color: var(--clr-transp-white);
  font-size: var(--body-2-size);
  line-height: var(--body-2-line);
  font-weight: 500;
}

.error {
  color: var(--clr-red);
  font-style: italic;
  font-size: var(--body-2-size);
  margin-top: -5px;
}

@media screen and (max-width: 1440px) {
  .contact {
    max-width: 90%;
  }
}

@media screen and (max-width: 1024px) {
  .contact {
    flex-direction: column;
    padding: 0;
    gap: 3rem;
    align-items: center;
  }

  .contact-infos h1,
  .contact-infos h2 {
    text-align: center;
  }
}
</style>
