<template>
  <article>
    <div>
        <h1>{{ title }}</h1>
        <p>{{ description }}</p>
    </div>
  </article>
</template>

<script>
export default {
  data() {
    return {
        title: "Welcome to my Website",
        description: "I cordially welcome you to my website!"
    }
  }
}
</script>

<style scoped>
  p {
    padding: 20px;
  }
</style>