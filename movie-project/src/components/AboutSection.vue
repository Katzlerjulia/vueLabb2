<script setup>

</script>
<script>
    export default {
        data() {
            return {
                name: '',
                renderName: false,
                imageSource: 'src/assets/CinemaImg.jpg'
            }
        },
        methods: {
            onClick() {
                this.renderName = true
            }
        }
    }
</script>

<template>
    <div>
        <img alt="" :src="imageSource" />
        <div class="textStyle">
            <h1>God kväll!</h1>
            <p>Vänlig skriv in ditt namn för mer info.</p>
            <input class="nameinput" v-model="name" />
            <input
                class="button"
                type="button"
                @click="onClick"
                value="lägg till"
            />
            <p v-if="renderName">
                Hej {{ name }}, vad kul att du hittat hit! <br />
                Du kan använda den här sidan till att få förslag på serier.
                <br />
                Du kan klicka på se hela listan, därefter kan du klicka på
                random serie för att slumpa fram en serie istället. <br />
                <br />
                Sen kan du refresha för att gå tillbaka till hela listan igen.
            </p>
            <p v-else></p>
        </div>
    </div>
   
</template>

<style scoped>
    .textStyle {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        background-color: white;
        color: #252525;
        padding: 3em;
        border-radius: 7px;
        text-align: center;
    }
    .button {
        background-color: white;
        border: none;
        padding: 3px 7px 3px 7px;
        margin-left: 2px;
        border-radius: 7px;
        cursor: pointer;
        border: 3px solid #252525;
    }
    .nameinput {
        border: none;
        border-radius: 7px;
        padding: 3px 7px 3px 7px;
        border: 3px solid #252525;
    }
    img {
        width: 100%;
        height: 100%;
    }
</style>
