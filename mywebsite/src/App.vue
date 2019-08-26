<template>
  <div id="app">
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)">
        <a slot="home" id="home" v-on:click="component = 'front-page'">Home</a>
        <a slot="about" id="about" v-on:click="component = 'about'">About</a>
        <a slot="gallery" id="gallery" v-on:click="component = 'app-gallery'">Gallery</a>
        <a slot="blog" id="blog" v-on:click="component = 'app-add-blog'">Blog</a>
        <a slot="contact"  id="contact" v-on:click="component = 'form-helper'">Contact</a>
    </app-header>
    <!--
    <h1>{{ title }}</h1>
    <p>{{ greeting() }}</p>
    -->
    <div id="main">
      <keep-alive>
        <component v-bind:is="component"></component>
      </keep-alive>
    </div>
    <app-footer id="footer" v-bind:title="title"></app-footer>
    <link href="https://fonts.googleapis.com/css?family=Noto+Sans&display=swap" rel="stylesheet">
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Gallery from './components/Gallery.vue'
import Frontpage from './components/Frontpage.vue'
import About from './components/About.vue'
import formHelper from './components/formHelper.vue'
import addBlog from './components/addBlog.vue'

export default {
  name: 'app',
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-gallery': Gallery,
    'form-helper': formHelper,
    'front-page': Frontpage,
    'about': About,
    'app-add-blog': addBlog
  },
  data() {
    return {
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
  * {
    font-family: 'Noto Sans', sans-serif;
  }
  button, input, textarea, form {
        outline: none;
    }
  h1, h2 {
    color: #0070d1;
    text-align: center;
  }
  #submit-button {
    position: relative;
  }
  article {
    border-style: solid;
    border: 2px solid #0070d1;
    margin: 10px auto;
    border-radius: 10px;
    width: 50%;
    padding: 10px;
    min-height: 35em;
  }
  #main {
    overflow: auto;
    padding-bottom: 100px;
    max-height: 70%;
  }
  #footer {
    position: relative;
    left: 0;
    bottom: 0;
    width: 100%;
    color: white;
    text-align: center;
    clear: both;
  }
  #main {
    transition: 5s;
  }
</style>
