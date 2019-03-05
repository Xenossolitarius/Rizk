<template>
    <div id="lobby-all" class="lobby-all" ref="container">
        <div id="category-container" class="category-container">

            <div id="games-a-z" class="games-a-z" style="display: block;">
                <h2 class="categoryTitle">All games</h2>
                    <ul class="game-grid search-grid" id="a-z-list">

                    </ul>
            </div>



            <div id="game-categories" class="game-categories" >
                <div v-for="category in categories" v-bind:key="category.id">                    
                    <SingleCategory v-bind:category="category" v-on:incrise-games="incriseGames"/>                    
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import SingleCategory from './SingleCategory'
import _ from 'lodash'

//testing--will delete
import MY_JSON from '../../data/mockData.json'


//
export default {
    name:"CategoryContainer",
    myJson: MY_JSON,
    data(){
        return {
            categories: [],
            numOfCat: 0,
            

        }

    },
    components:{
        SingleCategory
    },
    methods: {
      
        getNumPerCat(){ 

           return Math.floor(this.$refs.container.clientWidth/200);           

        },
        getNumOfCat(){
            return this.numOfCat;
        },
       scroll() {
           let func = this.getSingleCategory.bind(this);
           let numOfCat = this.getNumOfCat.bind(this);
           let getNumPerCat = this.getNumPerCat.bind(this);

            window.onscroll = _.throttle(function(){
                
                let scrollY = window.scrollY;
                let visible = document.documentElement.clientHeight;
                let pageHeight = document.documentElement.scrollHeight;
                let bottomOfPage = visible + scrollY >= pageHeight-400;
                let condition = bottomOfPage || pageHeight < visible;
            
                if (condition) {  
                    
                    func(getNumPerCat(),numOfCat());
                                      
                }
            
            },1000);
        },  
        incriseGames(cat){
            
            let idCat;
                switch (cat){
                    case 'elite':
                    idCat = 0
                    break;
                    case 'trending':
                    idCat = 1
                    break;
                    case 'jackpot':
                    idCat = 2
                    break;
                    case 'race':
                    idCat = 3
                    break;
                    case 'sports': 
                    idCat = 4
                    break;
                    default:
                    return;
                }
            
            let category = [];
            let num = this.getNumPerCat();
            let offset = this.categories[idCat].length;
            
              for(let i = 0; i < this.$options.myJson.length; i++){
                   if(cat == this.$options.myJson[i].cat && offset != 0){

                        offset--;                        
                        continue;
                    }
                    if(cat == this.$options.myJson[i].cat && num > 0){

                        num--;                        
                        category.push(this.$options.myJson[i]);
                        
                    }

                }
                
            
            this.categories[idCat].push(...category);
           
           
            
        },
        getSingleCategory(num,numOfCat){

               let category = [];
               let catName;
               
               
                switch (numOfCat){
                    case 0:
                    catName = 'elite'
                    break;
                    case 1:
                    catName = 'trending'
                    break;
                    case 2:
                    catName = 'jackpot'
                    break;
                    case 3:
                    catName = 'race'
                    break;
                    case 4: 
                    catName = 'sports'
                    break;
                    default:
                    this.$emit('show-footer');
                    return;
                }


                for(let i = 0; i < this.$options.myJson.length; i++){
                    if(catName == this.$options.myJson[i].cat && num > 0){
                        num--;
                        category.push(this.$options.myJson[i]);
                        
                    }

                }
                this.categories.push(category);
                this.numOfCat++;
                

           
        }
    },
    created(){
        
  

        
    },
    mounted(){

        let numCat = this.getNumPerCat();

        this.getSingleCategory(numCat,this.numOfCat);
        this.getSingleCategory(numCat,this.numOfCat);
        this.getSingleCategory(numCat,this.numOfCat);
       
       this.scroll();
    }
}
</script>

