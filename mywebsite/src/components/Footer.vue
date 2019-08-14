<template>
    <h1>{{ copyright }}</h1>
</template>

<script>
export default {
  data() {
    return {
        copyright: "Joonas Heinonen (C) 2019"
    }
  }
}
</script>

<style scoped>
    header {
        background: lightgreen;
        padding: 10px;
    }
    h1 {
        color: #222;
        text-align: center;
    }
</style>