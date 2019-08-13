<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <p>{{ greeting() }}</p>
    <ul>
      <li><a href="/" target="_blank">Titelseite</a></li>
      <li><a href="/" target="_blank">Über mich</a></li>
      <li><a href="/" target="_blank">Galerie</a></li>
      <li><a href="/" target="_blank">Kontakt</a></li>
    </ul>
    <ancestors></ancestors>
  </div>
</template>

<script>
import Website from './Website.vue'

export default {
  name: 'app',
  components: {
    'ancestors': Website
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
    background-color: blue;
  }
</style>
