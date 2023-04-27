<template>
  <div id="app">
    <div class="global-web-page">
      <router-view />
    </div>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Livvic:wght@300;400;500;600;700;900&display=swap');
:root {
  /* COLORS */
  --clr-midnight-green: #014e56;
  --clr-police-blue: #2c6269;
  --clr-deep-jungle-green: #004047;
  --clr-rapture-blue: #79c8c7;
  --clr-dark-green: #002529;
  --clr-sacramento-state-green: #012f34;
  --clr-light-coral: #f67e7e;
  --clr-red: #ff6f5b;
  --clr-white: #ffffff;
  --clr-trans-black: hsla(0, 100%, 0%, 0.5);

  /* FONTS */
  --font-family: 'Livvic', sans-serif;
  --h1-big-size: 6.25rem;
  --h1-big-line: 6.25rem;
  --h1-small-size: 4rem;
  --h1-small-line: 3.5rem;
  --h2-size: 3rem;
  --h2-line: 3rem;
  --h3-size: 1.125rem;
  --h3-line: 1.75rem;
  --body-1-size: 1.125rem;
  --body-1-line: 1.75rem;
  --body-2-size: 0.938rem;
  --body-2-line: 1.563rem;

  /* VARIOUS SIZES */
  --navBar-width: 69.375rem;
  --max-width: 90rem;
  --home-padding: 7rem;
}

* {
  margin: 0;
  padding: 0;
  list-style: none;
  text-decoration: none;
  border: none;
  box-sizing: border-box;
  font-family: var(--font-family);
}

 /* ####### A REMOVE */
*:focus {
  outline: 3px solid yellow;
}

button {
  display: block;
}

img {
  max-width: 100%;
  display: block;
}
</style>
