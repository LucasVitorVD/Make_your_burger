<template>
    <div id="main-banner">
        <h1>Make Your Burger</h1>
    </div>
</template>

<script>
    export default {
        name: 'Banner'
    }
</script>

<style scoped>
 #main-banner {
    display: flex;
    align-items: center;
    background-image: url('/public/img/burger_banner.jpg');
    background-position: 0 -350px;
    background-size: cover;
    height: 550px;
 }

 #main-banner h1 {
    background-color: #222;
    color: white;
    font-size: 3.5em;
    padding: 20px 40px;
 }
</style>