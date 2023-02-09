<script setup>
    import axios from 'axios'
</script>

<script>
    export default {
        data() {
            return {
                list: [],
                heroText: 'Vad vill du se ikväll?',
                randomSerie: null
            }
        },
        methods: {
            fetchData() {
                axios.get('src/assets/data.json').then((resp) => {
                    this.list = resp.data
                    console.log(this.list)
                })
            },
            getRandomSerie() {
                this.randomSerie =
                    this.list[Math.floor(Math.random() * this.list.length)]
            }
        }
    }
</script>

<template>
    <div class="hero-image">
        <div class="hero-text">
            <h1>{{ heroText }}</h1>
            <input @click="fetchData" type="button" value="Se hela listan" />
            <input @click="getRandomSerie" type="button" value="Random serie" />
        </div>
    </div>
    <div v-if="randomSerie" class="RandomContainer">
        <p>
            {{ randomSerie.show }}, {{ randomSerie.score }},
            {{ randomSerie.stream }}
        </p>
    </div>
    <div v-else class="ContainerList">
        <div v-for="item in list" :key="item.list">
            <p>{{ item.show }}, {{ item.score }}, {{ item.stream }}</p>
        </div>
    </div>
</template>

<style scoped>
    .hero-image {
        background-image:linear-gradient(rgba(0, 0, 0, 0.60), rgba(0, 0, 0, 0.60)), url('../assets/HeroImg.jpg');
        background-color: black;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
        height: 20em;
    }
    .hero-text {
        text-align: center;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        color: white;
    }

    .ContainerList {
        margin-top: 5em;
        text-align: center;
    }
    .RandomContainer {
        margin-top: 7em;
        text-align: center;
    }

    input {
        border: none;
        padding: 10px;
        border-radius: 7px;
        margin: 3px;
        background-color: white;
        font-size: 0.8em;
        cursor: pointer;
    }
</style>
