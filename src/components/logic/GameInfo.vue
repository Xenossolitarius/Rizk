<template>
        <div class="game-info-container" id="game-info-container-2" style="display: block;">
                <div class="game-info" id="game-info-1" style="transform: translate3d(0px, 0px, 0px);">
                    <button name="close" class="close-fill" aria-hidden="true" @click="$emit('exit')" ></button>
                    <div class="game-info-right" v-bind:style="{backgroundImage: 'url('+getImgUrl()+')'}"></div>
                    <div class="game-info-left">
                        <h1>{{info.desc}}</h1>
                        <h3 class="h5"></h3>
                        <a class="btn btn-yellow url-real" href="/en/casino/temple-of-treasures-megaways/13595">Play for real</a>
                        <a class="btn btn-inactive-lighter url-fun" href="/en/casino/try/temple-of-treasures-megaways/13595">Play for fun</a>
                    </div>
                </div>
            </div>
</template>

<script>
export default {
    name: "GameInfo",
    props: ["info"],
    methods: {
        getImgUrl(){
            return require('../../assets/images/'+this.info.img+'.jpg')
        }
    },
   
    
    

}
</script>

<style scoped>
.close-fill {
    background: url(../../assets/modal-close-button.svg) no-repeat center;
}
</style>


