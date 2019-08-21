<template>
    <div>
        <h1>Please fill out our form...</h1>
        <form>
            <div id="form-header"></div>
                <slot name="form-header"></slot>
            <div id="form-fields">
                <slot name="form-fields"></slot>
            </div>
            <div id="form-controls">
                <slot name="form-controls"></slot>
            </div>
            <div id="useful-links">
                <ul>
                    <li><a href="#">Link 1</a></li>
                    <li><a href="#">Link 2</a></li>
                    <li><a href="#">Link 3</a></li>
                    <li><a href="#">Link 4</a></li>
                </ul>
            </div>
        </form>
    </div>
</template>

<script>
export default {
  components: {

  },
  data() {
      return {

      }
  },
  methods: {

  }
}
</script>

<style scoped>
    h1 {
        color: red;
        text-align: center;
    }
    button {
        border: none;
        font-style: bold;
        color: white;
        background-color: red;
        padding: 10px 15px 10px 15px;
        margin: 10px;
        border-radius: 6px;
    }
</style>