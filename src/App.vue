<template>
  <div id="app">
    <Header />
    <Main />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    Main,
  },
};
</script>

<style lang="scss">
@import './assets/scss/style.scss';
// import font montserrat
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500&display=swap');
#app {
  min-width: 1750px;
  width: 100vw;
  font-family: 'Montserrat', sans-serif;
  font-size: 100%;
}
</style>
