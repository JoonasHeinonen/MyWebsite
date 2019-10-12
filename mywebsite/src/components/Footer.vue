<template>
    <footer> 
        <h1>{{ copyright }}  {{ title }}</h1>
        <p>Contact me on social media</p>
        <ul>
            <div class="someIcons" v-for="someIcon in someIcons">
                <li>
                    <!-- -->
                    <a class="some-icon" v-bind:href="`${someIcon.link}`">
                        <img class="some-icon" v-show="someIcon.show" v-bind:src="`../src/assets/some_logos/${someIcon.id}.png`">
                    </a>
                </li>
            </div>
        </ul>
    </footer> 
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
        
    },
    data() {
        return {
            copyright: "Copyright 2019",
            someIcons: [
                {id: 0, title: 'GitHub',    link: 'https://github.com/JoonasHeinonen',                      show: true}, // Github
                {id: 1, title: 'Instagram', link: 'https://www.instagram.com/j.girdeux/',                   show: true}, // Instagram
                {id: 2, title: 'LinkedIn',  link: 'https://www.linkedin.com/in/joonas-heinonen-32b6b414b/', show: true}, // LinkedIn
            ]
        }
    },
    created() {
        bus.$on('titleChanged', (data) => {
            this.title = data;
        });
    }
}
</script>

<style scoped>
    ul {
        list-style-type: none;
        margin: 0;
        overflow: hidden;
        background-color: white;
        display: flex;
        justify-content: center;
    }

    li {
        float: left;
    }

    li a {
        color: white;
        text-align: center;
        text-decoration: none;
        padding-left: 0;
    }

    h1 {
        color: #0070d1;
        text-align: center;
    }
    .some-icon {
        width: 40%;
        height: 40%;
    }

    p {
        color: black;
    }
</style>