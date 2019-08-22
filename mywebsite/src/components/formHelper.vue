<template>
    <div>
        <h1>Please fill out our form...</h1>
        <form>
                <div>
            <h3>Form</h3>
            <p>Please fill in the form!</p>
        </div>
        <div>
            <input type="text" placeholder="name" required />
            <input type="email" placeholder="email" required /> <br />
        </div>
        <div>
            <textarea id="subject" name="subject" placeholder="Write something.." style="margin-top: 10px; resize: none; height:200px; width: 344px;"></textarea><br />
            <button id="submit-button" v-on:click="handleSubmit">Submit!</button>
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
    handleSubmit: function() {
      alert("Thank you for your message!");
    }
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