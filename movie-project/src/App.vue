<script setup>
    import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
    <header>
        <div class="wrapper">
            <nav>
                <RouterLink to="/">Hem</RouterLink>
                <RouterLink to="/about">Om</RouterLink>
            </nav>
        </div>
    </header>
    <RouterView />
</template>

<style scoped>
    header {
        background-color: white;
        display: flex;
    }

    nav {
        width: 100%;
        text-align: right;
        margin-left: 10px;
        font-size: 12px;
        padding: 1rem 0;
    }
    nav a.router-link-exact-active {
        font-size: 2em;
    }

    nav a.router-link-exact-active:hover {
        background-color: transparent;
    }

    nav a {
        display: inline-block;
        padding: 0 1rem;
        border-left: 2px solid red;
        text-decoration: none;
        color: #252525;
    }
</style>
