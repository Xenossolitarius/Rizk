<template>
    <div class="cat">
        <h2 class="categoryTitle" id="title-1">{{category[0].cat}}</h2>

            <div class="category-desktop" id="category-1">
                <div class="navi-arrow navi-arrow-left" @click="slideLeft"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                    <div class="navi-arrow navi-arrow-right" @click="slideRight"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                        <ul class="categoryRow categoryRowDesktop clearfix transition" id="categoryrow-1"  v-bind:style="{left: position +'px' }" >                            
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
            infoDiagProps: this.category[0],
            position: 0,
            numOfGames: 0,
            gameSum:0,

        }

    },
    methods: {
        changeInfo(id){
            
            this.infoDiagProps =  this.category.find(obj =>{return obj.id === id});
            this.showInfoDiag = true;
            
        },
        closeInfo(){
            this.showInfoDiag = false;
        },

        slideRight(){
            let tempPos = this.position - 200*this.numOfGames;
            this.$emit('incrise-games',this.category[0].cat);
            this.gameSum += this.numOfGames;

            if(this.gameSum < this.category.length){
                


                this.position = tempPos;
            }
        },
        slideLeft(){
            let tempPos = this.position + 200*this.numOfGames;
            if(tempPos <= 0){
            this.position = tempPos;
            }
        }
       
        
    },
    mounted(){
        this.numOfGames = this.category.length;
    }
}
</script>

<style scoped>
.navi-arrow:hover{
    opacity: 1;
}

.categoryRow.categoryRowDesktop {
    position: relative;

}

.transition{
    
  -webkit-transition: left 0.5s ease-out;  /* Chrome 1-25, Safari 3.2+ */
     -moz-transition: left 0.5s ease-out;  /* Firefox 4-15 */
       -o-transition: left 0.5s ease-out;  /* Opera 10.50–12.00 */
          transition: left 0.5s ease-out;  /* Chrome 26, Firefox 16+, IE 10+, Opera 12.10+ */

}

</style>



