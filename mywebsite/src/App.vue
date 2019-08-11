<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ title }}</h1>
    <p>{{ greeting() }}</p>
    <ul>
      <li><a href="/" target="_blank">Titelseite</a></li>
      <li><a href="/" target="_blank">Über mich</a></li>
      <li><a href="/" target="_blank">Galerie</a></li>
      <li><a href="/" target="_blank">Kontakt</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'app',
  data: function () {
    return {
      title: 'Herzlich willkommen auf meiner Website!'
    }
  },
  methods: {
    greeting: function() {
      return "Guten tag, Gast!";
    }
  }
}
</script>

<style>

</style>
