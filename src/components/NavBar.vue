<template>
    <header>
        <nav>
            <router-link to="/">
                <img :src="logo" :alt="alt" id="logo">
            </router-link>
            <div>
                <router-link to="/">Home</router-link>
                <router-link to="/Pedidos">Pedidos</router-link>
            </div>
        </nav>
    </header>
</template>

<script>
    export default {
        name: 'NavBar',
        props: ['logo', 'alt']
    }
</script>

<style scoped>
    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #222;
        border-bottom: 4px solid #111;
        padding: 0.9rem 3.2rem;
    }

    #logo {
        width: 40px;
        height: 40px
    }

    nav a {
        color: #FCBA03;
        text-decoration: none;
        margin: .6rem;
        transition: .3s;
    }

    nav a:hover {
        color: white;
    }
</style>