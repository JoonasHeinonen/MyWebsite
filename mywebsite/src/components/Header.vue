<template>
    <header>
        <div class="header-div">
            <h1>{{ title }}</h1>
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
        border-color:grey;
        border-style: solid;
        border-width: 1px 0 1px 0;
        background-color: white;
        width: 100%;
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
        margin: 0 auto;
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
        margin: 1em 1em 2em 1em;
        padding: 1em;
        font-size: 20px;
    }
</style>