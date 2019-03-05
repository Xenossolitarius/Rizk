<template>
    <div class="animated fadeIn">
        <div class="hover">
            <a class="btn-play">
                <div class="tri"></div>
            </a>
        </div>
        <a href="https://rizk.com/en/casino/temple-of-treasures-megaways/13595">
            <img class="game-img" v-bind:src="require('../../assets/images/'+ game.img +'.jpg')" width="190" height="190" v-bind:alt="game.desc" style="opacity: 1;">
        </a>
		<a @click="$emit('change-info',game.id)" class="readmore" ></a>      
    </div>
</template>

<script>
export default {
    name:"SingleGame",
    props: ["game"],
    
}
</script>

<style scoped>
.readmore {
    background: url(../../assets/show-more-button.svg) no-repeat center;
}
.readmore:hover{
    opacity: 1;
}

 .animated {
            -webkit-animation-duration: 6s;
            animation-duration: 6s;
            -webkit-animation-fill-mode: both;
            animation-fill-mode: both;
         }
         
         @-webkit-keyframes fadeIn {
            0% {opacity: 0;}
            100% {opacity: 1;}
         }
         
         @keyframes fadeIn {
            0% {opacity: 0;}
            100% {opacity: 1;}
         }
         
         .fadeIn {
            -webkit-animation-name: fadeIn;
            animation-name: fadeIn;
         }



</style>

