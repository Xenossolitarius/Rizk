<template>
    <div class="cat">
        <h2 class="categoryTitle" id="title-1">{{category[0].cat}}</h2>

            <div class="category-desktop" id="category-1">
                <div class="navi-arrow navi-arrow-left"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                    <div class="navi-arrow navi-arrow-right"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                        <ul class="categoryRow categoryRowDesktop clearfix" id="categoryrow-1">                            
                            <li v-for="game in category" v-bind:key="game.id">                                
                                <SingleGame v-bind:game="game" v-on:change-info="changeInfo"/>                                
                            </li>                          
                        </ul>
            </div>
        
        <GameInfo v-bind:showInfo="showInfoDiag" v-bind:info="infoDiagProps" v-on:close-info="closeInfo"/>
     

    </div>
         
</template>

<script>
import SingleGame from './SingleGame'
import GameInfo from './GameInfo'


export default {
    name:"SingleCategory",
    components:{
        SingleGame,
        GameInfo
    },
    props: ["category"],
     data(){
        return {
            showInfoDiag: false,
            infoDiagProps: this.category[0]

        }

    },
    methods: {
        changeInfo(id){
            
            this.infoDiagProps =  this.category.find(obj =>{return obj.id === id});
            this.showInfoDiag = true;
            
        },
        closeInfo(){
            this.showInfoDiag = false;
        }
       
        
    }
}
</script>

<style scoped>
.navi-arrow:hover{
    opacity: 1;
}



</style>



