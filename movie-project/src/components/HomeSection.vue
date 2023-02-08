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
<p>{{ randomSerie.show }}, {{ randomSerie.score }}, {{ randomSerie.stream }}</p>
    </div>
    <div v-else class="ContainerList">
        <div v-for="item in list" :key="item.list">
            <p>{{ item.show }}, {{ item.score }}, {{ item.stream }}</p>
        </div>
    </div>
</template>

<style scoped>

    .hero-image {
        background-image: url('../assets/HeroImage.jpg');
        background-color: red;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
        height: 25em;
    }
    .hero-text {
        text-align: center;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        color: white;
        font-family: sans-serif;
    }

        .ContainerList {
        font-family: sans-serif;
        color: #252525;
        margin-top: 7em;
        text-align: center;
        font-size: 1.2em;
    }
     .RandomContainer {
        font-family: sans-serif;
        color: #252525;
        margin-top: 7em;
        text-align: center;
        font-size: 1.2em;
    }

    input {
        border: none;
        padding: 10px;
        border-radius: 7px;
        margin: 3px;
        background-color: white;
        color: #252525;
        font-size: .8em;
       cursor: pointer;
    }
</style>
