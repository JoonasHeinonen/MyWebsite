<template>
    <footer> 
        <h1>{{ copyright }}  {{ title }}</h1>
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
    data() {
        return {
            copyright: "Copyright 2019"
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
    header {
        background: lightgreen;
        padding: 10px;
    }
    h1 {
        color: #222;
        text-align: center;
    }
</style>