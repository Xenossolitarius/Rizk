<template>
  <div id="app">

    <Spinner v-if="spinIt" />
 

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
    },5000);
  }
}
</script>

<style src="./style/style.css">

</style>
