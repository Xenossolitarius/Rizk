<template>
    <div class="cat">
        <h2 class="categoryTitle" id="title-1">{{category[0].cat}}</h2>

            <div class="category-desktop" id="category-1">
                <div class="navi-arrow navi-arrow-left"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                    <div class="navi-arrow navi-arrow-right"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                        <ul class="categoryRow categoryRowDesktop clearfix" id="categoryrow-1">
                            <li v-for="game in category" v-bind:key="game.id">
                                <SingleGame v-bind:game="game" v-on:show-info="showInfo"/>
                            </li>
                        </ul>
            </div>

        <GameInfo v-if="showInfoDiag" v-bind:info="infoDiagProps" v-on:exit="closeInfo"/>

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
            infoDiagProps: {}

        }

    },
    methods: {
        showInfo(id){
            
            this.infoDiagProps =  this.category[id-1];
            this.showInfoDiag = true;
            
        },
        closeInfo(){
            
            this.showInfoDiag = false;
        }
        
    }
}
</script>

