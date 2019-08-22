<template>
    <div>
        <h1>Gallery</h1>
        <ul>
            <li v-for="article in articles" v-on:click="article.show = !article.show">
                <h1>{{ article.title }} </h1>
                <img v-show="article.show" v-bind:src="`../media/images/${article.id}.jpg`">
                
                <p class="divider" v-show="article.show">{{ article.description }}</p>
            </li>
        </ul>
        <!--
        <button v-on:click="deletePic">Delete picture</button>
        -->
    </div>
</template>

<script>
export default {
    props: {
        articles: {
            type: Array,
            required: true
        }
    },
    data() {
        return {

        }
    },
    methods: {
        deletePic: function() {
            this.articles.pop();
        }
    },
    /*
    // lifecycle hooks
    beforeCreate() {
        alert("beforeCreate()");
    },
    created() {
        alert("created()");
    },
    beforeMount() {
        alert("beforeMount()");
    },
    mounted() {
        alert("mounted()");
    },
    beforeUpdate() {
        alert('beforeUpdate()');
    },
    updated() {
        alert('updated()');
    }
    */
}
</script>

<style scoped>

p {
    font-family: scriptina;
}
h1, h2, h3 {
    color: black;
    font-style: italic;
}
#articles {
    width: 100%;
    max-width: 1200px;
    margin: 40px auto;
    padding: 0 20px;
    box-sizing: border-box;
}
img {
    width: 75%;
    height: 75%;
}
ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
    color: #0070d1;
}
li {
    flex-grow: 1;
    flex-basis: 200px;
    text-align: center;
    padding: 30px;
    border: 2px solid #0070d1;
    margin: 5px;
    border-radius: 10px;
}
.divider {
    border-width: 2px 0 0 0;
    border-style: solid;
}
</style>