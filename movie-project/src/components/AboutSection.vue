<script setup></script>
<script>
    export default {
        data() {
            return {
                name: '',
                renderName: false
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
            Du kan använda den här sidan till att få förslag på serier. <br />
            Du kan klicka på se hela listan, därefter kan du klicka på random
            serie för att slumpa fram en serie istället. <br />
            <br />
            Sen kan du refresha för att gå tillbaka till hela listan igen.
        </p>
        <p v-else></p>
    </div>
</template>

<style scoped>
    .textStyle {
        margin-top: 9em;
        align-items: center;
        margin-left: auto;
        margin-right: auto;
        text-align: center;
    }
    .button {
        background-color: white;
        border: none;
        padding: 3px 7px 3px 7px;
        margin-left: 2px;
        border-radius: 7px;
        cursor: pointer;
    }
    .nameinput {
        border: none;
        border-radius: 7px;
        padding: 3px 7px 3px 7px;
    }
</style>
