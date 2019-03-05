<template>
  <div id="app">

    <transition name="fade">
    <Spinner v-if="spinIt" />
    </transition>

    <SideMenu />
    <LoadWindow />
  </div>
</template>

<script>

import SideMenu from './components/layouts/SideMenu.vue'
import LoadWindow from './components/LoadWindow.vue'
import Spinner from './components/layouts/Spinner.vue'
import { setTimeout } from 'timers';

export default {
  name: 'app',
  components: {
    SideMenu,
    LoadWindow,
    Spinner
  },
  data(){
    return {
      spinIt: true
    }
  },
  methods:{

  },
  mounted(){
    setTimeout(()=>{
      this.spinIt= false;
      
    },3000);
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

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
  opacity: 1;
}
</style>
