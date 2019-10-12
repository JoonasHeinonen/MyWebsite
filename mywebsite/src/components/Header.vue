<template>
    <header>
        <div class="header-div">
            <h1 v-on:click="changeTitle">{{ title }}</h1>
            <ul>
                <slot name="home"></slot>
                <slot name="projects"></slot>
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
    ul, header {
        display: flex;
        justify-content: center;
    }
    header {
        padding: 10px;
        border-color: #555555;
        border-style: solid;
        border-width: 0 0 1px 0;
        margin: 0px auto;
    }
    .header-div {
        width: 80%;
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
    a {
        border-style: solid;
        border-width: 2px;
        border-color: #555555;
        border-radius: 45px;
        min-width: 100px;
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