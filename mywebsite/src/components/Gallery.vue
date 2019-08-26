<template>
    <div v-bind:articles="articles">
        <article>
            <h1>Gallery</h1>
            <ul>
                <div class="images" v-for="image in images">
                    <h2 v-on:click="image.show = !image.show">{{ image.title }}</h2>
                    <img v-show="image.show" v-bind:src="`../media/images/${image.id}.jpg`">
                    <p class="divider" v-show="image.show">{{ image.description }}</p>
                </div>
            </ul>
        </article>
        <link href="https://fonts.googleapis.com/css?family=Italianno|Noto+Sans&display=swap" rel="stylesheet">
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
            images: [
                {id: 0, title: 'Jäger', description: 'Mein Großonkel und mein Großvater jagen.', show: false},
                {id: 1, title: 'Mein Großonkel', description: 'Mein Großonkel während des Krieges.', show: false},
                {id: 2, title: 'In Karelien', description: 'Sie sind in Karelien', show: false},
            ]
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
article {
    width: 80%;
}
p {
    font-family: scriptina;
}
h2, h3 {
    color: black;
    font-size: 80px;
    font-family: 'Italianno', cursive;
    transition: 0.2s;
}
h2:hover {
    color: #222222;
    cursor: pointer;
}
#articles {
    width: 100%;
    margin: 40px auto;
    padding: 0 20px;
    box-sizing: border-box;
}
img {
    width: 100%;
}
ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
    color: #0070d1;
}
.images {
    flex-grow: 1;
    flex-basis: 200px;
    text-align: center;
    padding: 0px;
    border: 2px solid #0070d1;
    margin: 5px;
    border-radius: 10px;
}
.divider {
    border-width: 2px 0 0 0;
    border-style: solid;
}
</style>