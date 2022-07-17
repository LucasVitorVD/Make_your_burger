<template>
  <div class="container">
    <NavBar :logo="logo_src" :alt="app_name"/>
    <router-view/>
    <Footer></Footer>
  </div>
</template>

<script>
  import NavBar from './components/NavBar'
  import Footer from './components/Footer'

  export default {
    name: 'App',
    components: {
      NavBar,
      Footer
    },
    data() {
      return {
        logo_src: '/img/logo.png',
        app_name: 'Make your burger'
      }
    }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Helvetica;
  }

  main {
    margin: 3.4rem;
    min-height: 60vh;
  }

  h1 {
    text-align: center;
    font-size: 2.6em;
    margin-bottom: 1.2rem;
    color: #222;
  }
</style>