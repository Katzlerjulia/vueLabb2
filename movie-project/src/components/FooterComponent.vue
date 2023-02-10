<script setup></script>

<script>
    import FooterMessage from './FooterMessage.vue'

    export default {
        components: {
            FooterMessage
        }
    }
</script>

<template>
    <div class="footer">
        <footer-message message="Hello, this page is made in vue and vite!" />
        <p> <i>Hoppas du gillar nån serie</i> </p>
    </div>

</template>

<style scoped>
    .footer {
        position: fixed;
        left: 0;
        bottom: 0;
        width: 100%;
        background-color: #202020;
        color: white;
        text-align: center;
        font-size: 15px;
        padding: 3em;
    }
</style>
