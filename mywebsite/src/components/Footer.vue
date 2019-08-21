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
        background: #0070d1;
        padding: 10px;
        width: 100%;
    }
    h1 {
        color: #0070d1;
        text-align: center;
    }
</style>