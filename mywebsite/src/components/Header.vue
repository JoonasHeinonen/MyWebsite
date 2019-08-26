<template>
    <header>
        <h1 v-on:click="changeTitle">{{ title }}</h1>
        <div>
            <ul>
                <slot name="home"></slot>
                <slot name="about"></slot>
                <slot name="gallery"></slot>
                <slot name="blog"></slot>
                <slot name="contact"></slot>
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
        padding: 10px;
        height: 100px;
        border-color: #555555;
        border-style: solid;
        border-width: 0 0 1px 0;
        margin: 0px auto;
    }
    h1, a {
        color: #555555;
        transition: 0.2s;
        text-align: center;
    }
    ul, a {
        width: 50%;
        margin: auto;
    }
    a:hover {
        color: #cccccc;
        transition: 0.5s;
        cursor: pointer;
    }
    a {
        text-decoration: none;
        margin: 1em;
        padding: 1em;
        font-size: 20px;
    }
</style>