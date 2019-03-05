<template>
    <div id="rizk-loader" class="rizk-loader loading" style=""><img src="../../assets/wor-loader-icon.png" alt="Rizk loading" class="loader-wheel"></div>
</template>

<script>
export default {
    name:'Spinner'
}
</script>

<style  scoped>
.loading:before {
  content: '';
  display: block;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgb(0, 0, 0);
}

</style>

