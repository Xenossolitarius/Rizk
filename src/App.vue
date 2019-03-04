<template>
  <div id="app">
    <SideMenu />
    <AllContent />
  </div>
</template>

<script>

import SideMenu from './components/layouts/SideMenu.vue'
import AllContent from './components/AllContent.vue'

export default {
  name: 'app',
  components: {
    SideMenu,
    AllContent
  }
}
</script>

<style src="./style/style.css">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
