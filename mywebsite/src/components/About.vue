<template>
    <div>
        <article>
          <h1>{{ title }}</h1>
          <p>{{ info }}</p>
        </article>
    </div>
</template>

<script>
export default {
  data() {
    return {
        title: "About",
        info: "I am an IT enthousiast from Turku, South-Western Finland. "
    }
  }
}
</script>

<style scoped>
  p {
    padding: 20px;
  }
</style>