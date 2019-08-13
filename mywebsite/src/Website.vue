<template>
    <ul>
        <h2>meine Großeltern</h2>
        <li v-for="ancestor in ancestors">{{ ancestor }}</li>
    </ul>
</template>

<script>
export default {
  data() {
    return {
        ancestors: ['Eino', 'Frans', 'Abel', 'Väinö', 'Kustaa Aleksander']
    }
  }
}
</script>

<style>

</style>
