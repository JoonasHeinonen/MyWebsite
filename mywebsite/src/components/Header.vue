<template>
    <header>
        <h1 v-on:click="changeTitle">{{ title }}</h1>
        <button>Home</button>
        <button>About</button>
        <button>Gallery</button>
        <button>Contact</button>
    </header>
</template>

<script>
import { bus } from '../main';

export default {
    props: {
        title: {
            type: String
        }
    },
    methods: {
        changeTitle: function() {
            //this.$emit('changeTitle', 'Frans Heinonen');
            this.title = 'Frans Heinonen';
            bus.$emit('titleChanged', 'Frans Heinonen');
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