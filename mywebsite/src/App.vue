<template>
  <div id="app">
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)">
        <a slot="home" id="home" v-on:click="component = 'front-page'">Home</a>
        <a slot="about" id="about">About</a>
        <a slot="gallery" id="gallery" v-on:click="showGallery()">Gallery</a>
        <a slot="contact"  id="contact" v-on:click="component = 'form-helper'">Contact</a>
    </app-header>
    <!--
    <h1>{{ title }}</h1>
    <p>{{ greeting() }}</p>
    -->
    <keep-alive>
      <component v-bind:is="component"></component>
    </keep-alive>
    <app-gallery id="gallery-element" v-bind:articles="articles" style="visibility: hidden"></app-gallery>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Gallery from './components/Gallery.vue'
import Frontpage from './components/Frontpage.vue'
import formHelper from './components/formHelper.vue'

export default {
  name: 'app',
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-gallery': Gallery,
    'form-helper': formHelper,
    'front-page': Frontpage
  },
  data() {
    return {
      articles: [
            {id: 0, title: 'Jäger', description: 'Mein Großonkel und mein Großvater jagen.', show: false},
            {id: 1, title: 'Mein Großonkel', description: 'Mein Großonkel während des Krieges.', show: false},
            {id: 2, title: 'In Karelien', description: 'Sie sind in Karelien', show: false},
        ],
        title: "Joonas Heinonen",
        titteli: "Homopaska",
      component: 'front-page'
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
      } else if (hour >= 12 && hour < 17) {
        greet = "Guten tag, Gast!";
      } else if (hour >= 17 && hour < 22) {
        greet = "Guten abend, Gast!";
      }
      return greet;
    },
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle;
    },
    handleSubmit: function() {
      alert("Thank you for your message!");
    },
    showGallery: function() {
      this.component = 'app-gallery';
      let gallery = document.getElementById("gallery-element");
      gallery.style.visibility = "visible";
    }
  }
}
</script>

<style>
  h1, h2 {
    color: #0070d1;
  }
  #submit-button {
    position: relative;
  }
</style>
