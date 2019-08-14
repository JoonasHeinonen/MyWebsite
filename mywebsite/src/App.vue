<template>
  <div id="app">
    <app-header></app-header>
    <h1>{{ title }}</h1>
    <p>{{ greeting() }}</p>
    <app-gallery></app-gallery>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Header.vue'
import Gallery from './components/Gallery.vue'
import Frontpage from './components/Frontpage.vue'
export default {
  name: 'app',
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-gallery': Gallery
  },
  data() {
    return {
      title: 'Joonas Heinonen'
    }
  },
  methods: {
    greeting: function() {
      let today = new Date();
      let hour = today.getHours();
      let greet;
      if (hour >= 21 || hour <= 6) {
        greet = "Gute nacht, Gast!";
      } else if (hour >= 6 && hour < 12) {
        greet = "Guten morgen, Gast!";
      } else if (hour >= 12 < 17) {
        greet = "Guten tag, Gast!";
      } else if (hour >= 17 || hour < 22) {
        greet = "Guten abend, Gast!";
      }
      return greet;
    }
  }
}
</script>

<style>
  html {
    background-color: #549454;
  }
  h1, h2 {
    color: #66bb66;
  }
</style>
