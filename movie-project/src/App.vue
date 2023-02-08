<script setup>
    import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
    <header>
        <div class="wrapper">
            <nav>
                <RouterLink to="/">Home</RouterLink>
                <RouterLink to="/about">About</RouterLink>
            </nav>
        </div>


    </header>
    <RouterView />
</template>

<style scoped>
    header {
        line-height: 1.5;
        max-height: 100vh;
    }

    nav {
        width: 100%;
        font-size: 12px;
        text-align: center;
        margin-top: 2rem;
    }

    header {
        display: flex;
        place-items: center;
    }

    header .wrapper {
        display: flex;
        place-items: flex-start;
        flex-wrap: wrap;
    }

    nav {
        text-align: left;
        margin-left: -1rem;
        font-size: 1rem;

        padding: 1rem 0;
        margin-top: 1rem;
    }
    nav a.router-link-exact-active {
        color: #252525;
        font-size: 2em;
    }

    nav a.router-link-exact-active:hover {
        background-color: transparent;
    }

    nav a {
        display: inline-block;
        padding: 0 1rem;
        border-left: 1px solid red;
        font-family: sans-serif;
        text-decoration: none;
        color: #252525;
    }
</style>
