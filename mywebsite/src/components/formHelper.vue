<template>
    <div>
        <article>
            <div id="form-box">
                <h1>Please fill out our form...</h1>
                <form>
                <div>
                    <label>Name</label>
                    <input id="name" type="text" required />
                    <label>Email</label>
                    <input id="email" type="email" required />
                    <label>Subject</label>
                    <textarea id="subject" name="subject"></textarea><br />
                    <button id="submit-button" v-on:click="handleSubmit">SUBMIT</button>
                </div>
                </form>
            </div>
        </article>
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
        if(document.getElementById("name").value == '')
        {
            alert("debug name");
        } else if (document.getElementById("email").value == '')
        {
            alert("debug email");
        } else if (document.getElementById("subject").value == '')
        {
            alert("debug subject");
        } else {
            alert("Thank you for your message!");
        }
    }
  }
}
</script>

<style scoped>
    #form-box *{
        box-sizing: border-box;
    }
    #form-box {
        margin: 20px auto;
        max-width: 500px;
    }
    label {
        display: block;
        margin: 20px 0 10px;
    }
    input[type="text"], input[type="email"], textarea {
        display: block;
        width: 100%;
        padding: 8px;
        resize: none;
    }
    textarea {
        width: 100%;
    }
    h3 {
        margin-top: 10px
    }
    button {
        font-weight: bold;
        transition: 0.5s;
    }
    button:hover {
        background-color: rgb(255, 80, 80);
        transition: 0.5s;
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