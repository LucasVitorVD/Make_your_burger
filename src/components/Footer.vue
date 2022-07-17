<template>
    <footer>
        <p>Make Your Burger &copy; {{ date }}</p>
    </footer>
</template>

<script>
    export default {
        name: 'Footer',
        data() {
            return {
                date: new Date().getFullYear()
            }
        }
    }
</script>

<style scoped>
    footer {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 200px;
        background-color: #222;
        border-top: 4px solid #111;
        color: #FCBA03;
    }
</style>