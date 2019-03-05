<template>
    <div id="lobby-all" class="lobby-all">
        <div id="category-container" class="category-container">

            <div id="game-categories" class="game-categories" >
                <div v-for="category in categories" v-bind:key="category.id">                    
                    <SingleCategory v-bind:category="category" />                    
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
            numOfCat: 0

        }

    },
    components:{
        SingleCategory
    },
    methods: {
        getNumOfCat(){
            return this.numOfCat;
        },
       scroll() {
           let func = this.getSingleCategory.bind(this);
           let numOfCat = this.getNumOfCat.bind(this);

            window.onscroll = _.throttle(function(){
                
                let scrollY = window.scrollY;
                let visible = document.documentElement.clientHeight;
                let pageHeight = document.documentElement.scrollHeight;
                let bottomOfPage = visible + scrollY >= pageHeight-400;
                let condition = bottomOfPage || pageHeight < visible;
            
                if (condition) {  
                    
                    func(10,numOfCat(),0);
                                      
                }
            
            },1500);
        },
        getSingleCategory(num,numOfCat,offset){

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
                    return;
                }


                for(let i = 0; i < this.$options.myJson.length; i++){
                    if(catName == this.$options.myJson[i].cat && offset != 0){
                        offset--;
                        continue;
                    }
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
        this.getSingleCategory(10,this.numOfCat,0);
        this.getSingleCategory(10,this.numOfCat,0);
        this.getSingleCategory(10,this.numOfCat,0)

        
    },
    mounted(){
       
       this.scroll();
    }
}
</script>

