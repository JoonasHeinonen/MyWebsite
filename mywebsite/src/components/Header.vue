<template>
    <header>
        <h1 v-on:click="changeTitle">{{ title }}</h1>
        <div>
            <ul>
                <a href="#">Home</a>
                <a href="#">About</a>
                <a href="#">Gallery</a>
                <a href="#">Contact</a>
            </ul>
            
        </div>
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
        background: #0070d1;
        padding: 10px;
        height: 100px;
    }
    h1, a {
        color: white;
        transition: 0.2s;
        text-align: center;
    }
    ul, a {
        width: 50%;
        margin: auto;
    }        
    a:hover {
        color: #c4e3ff;
        transition: 0.5s;
    }
    a {
        text-decoration: none;
        margin: 20px;
        padding: 20px;
        font-size: 20px;
    }
</style>