<template>
    <div id="main">
        <ul>
            <li v-for="article in articles" v-on:click="article.show = !article.show">
                <h1>{{ article.title }} </h1>
                <img v-bind:src="`.../images/${article.id}.jpg`">
                
                <p v-show="article.show">{{ article.description }}</p>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  data() {
    return {
        articles: [
            {id: 0, title: 'Jäger', description: 'Mein Großonkel und mein Großvater jagen.', show: false},
            {id: 1, title: 'Mein Großonkel', description: 'Mein Großonkel während des Krieges.', show: false},
            {id: 2, title: 'In Karelien', description: 'Sie sind in Karelien', show: false},
        ]
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