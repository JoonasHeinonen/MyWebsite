<template>
    <div>
        <h1>{{ title }}</h1>
        <p>{{ description }}</p>
    </div>
</template>

<script>
export default {
  data() {
    return {
        title: "About",
        description: "I am me and you are you!"
    }
  }
}
</script>

<style scoped>
</style>