<template>
  <header>
    <h1>Fargo's Unified Wiki</h1>
  </header>
  <ItemsPage/>
</template>

<script>
import ItemsPage from './components/ItemsPage.vue'

export default {
  name: 'App',
  components: {
    ItemsPage
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;700&display=swap');

#app {
  font: 300 1rem 'Lato', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  margin: 10px;
  background-color: #DADADA;
  overflow: hidden;
}

header {
  text-align: center;
  font: 700 1rem 'Lato', sans-serif;
}
</style>
