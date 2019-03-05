<template>
    <div id="rizk-loader" class="rizk-loader loading animated fadeOut" style=""><img src="../../assets/wor-loader-icon.png" alt="Rizk loading" class="loader-wheel"></div>
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

 .animated {
            -webkit-animation-duration: 5s;
            animation-duration: 5s;
            -webkit-animation-fill-mode: both;
            animation-fill-mode: both;
         }
         
        @-webkit-keyframes fadeOut {
            0% {opacity: 1;}
            60% {opacity: 1;}
            100% {opacity: 0;}
         }
         
         @keyframes fadeOut {
            0% {opacity: 1;}
            60% {opacity: 1;}
            100% {opacity: 0;}
         }
         
         .fadeOut {
            -webkit-animation-name: fadeOut;
            animation-name: fadeOut;
         }


</style>

