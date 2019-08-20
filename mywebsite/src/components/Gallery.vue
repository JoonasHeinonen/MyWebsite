<template>
    <div id="main">
        <ul>
            <li v-for="article in articles" v-on:click="article.show = !article.show">
                <h1>{{ article.title }} </h1>
                <img v-show="article.show" v-bind:src="`../images/${article.id}.jpg`">
                
                <p v-show="article.show">{{ article.description }}</p>
            </li>
        </ul>
        <button v-on:click="deletePic">Delete picture</button>
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
    }
}
</script>

<style scoped>
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
}
li {
    flex-grow: 1;
    flex-basis: 300px;
    text-align: center;
    padding: 30px;
    border: 1px solid #222;
    margin: 10px;
}
</style>