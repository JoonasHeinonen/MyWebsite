<template>
  <div id="app">
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
    <h1>{{ title }}</h1>
    <p>{{ greeting() }}</p>
    <app-gallery v-bind:articles="articles"></app-gallery>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
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
      articles: [
            {id: 0, title: 'Jäger', description: 'Mein Großonkel und mein Großvater jagen.', show: false},
            {id: 1, title: 'Mein Großonkel', description: 'Mein Großonkel während des Krieges.', show: false},
            {id: 2, title: 'In Karelien', description: 'Sie sind in Karelien', show: false},
        ],
        title: "Joonas Heinonen"
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
    },
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle;
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
