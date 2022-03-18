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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  margin: 10px;
  background-color: #DADADA;
  overflow: hidden;
}

header {
  margin-bottom: 10px;
  text-align: center;
}
</style>
