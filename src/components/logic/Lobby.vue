<template>
    <div id="lobby-all" class="lobby-all" >
        <div id="category-container" class="category-container">

            <SearchContainer v-on:show-footer="showFooter" v-bind:filtered="filtered" v-if="!showCategory"/>


            <CategoryContainer v-on:show-footer="showFooter" v-if="showCategory"/>
    

        </div>
    </div>
</template>

<script>
import CategoryContainer from './CategoryContainer'
import SearchContainer from './SearchContainer'

import MY_JSON from '../../data/mockData.json'

export default {
    name: "Lobby",
    myJson: MY_JSON,
    components:{
        CategoryContainer,
        SearchContainer
    },
    props: ["filter"],
    data(){
        return{
            filtered: [],
            showCategory: true
        }
    },
    watch: {
        filter: {
            handler(newVal){
                if(newVal == 'abc'){
                    this.returnABC();
                }else if(newVal == 'jackpot'){
                    this.returnCat(newVal);
                }else if(newVal == 'race'){
                    this.returnCat(newVal);
                }else if(newVal == ''){
                    this.showCategory=true;
                }else{
                    this.returnSearch(newVal);
                }
            }
        }
    },
    methods: {
        showFooter(data){
            this.$emit('show-footer',data);
        },
        returnAll(){
            
            for(let i = 0; i < this.$options.myJson.length; i++){   

                this.filtered.push(this.$options.myJson[i]);    

            }
               
        },
        returnABC(){
            let tempFiltered=[];
             for(let i = 0; i < this.$options.myJson.length; i++){   

                tempFiltered.push(this.$options.myJson[i]);    

            }

            tempFiltered.sort(function(a, b){
                var x = a.desc.toLowerCase();
                var y = b.desc.toLowerCase();
                if (x < y) {return -1;}
                if (x > y) {return 1;}
                return 0;
                });

            while(this.filtered.length){
                this.filtered.pop();
            }
            
            this.filtered.push(...tempFiltered);
            this.showCategory=false;            
           
        },
        returnCat(cat){
            
            let tempFiltered=[];
             for(let i = 0; i < this.$options.myJson.length; i++){   

                tempFiltered.push(this.$options.myJson[i]);    

            }

           tempFiltered = tempFiltered.filter((item)=>{
                return item.cat == cat;
            });
            while(this.filtered.length){
                this.filtered.pop();
            }
            
            this.filtered.push(...tempFiltered);
            this.showCategory=false;   
        },
        returnSearch(input){
            
            let tempFiltered=[];
             for(let i = 0; i < this.$options.myJson.length; i++){   

                tempFiltered.push(this.$options.myJson[i]);    

            }

           tempFiltered = tempFiltered.filter((item)=>{
                return item.desc.toLowerCase().indexOf(input.toLowerCase()) > -1
            });
            while(this.filtered.length){
                this.filtered.pop();
            }
            
            this.filtered.push(...tempFiltered);
            this.showCategory=false;  



        }

        
    },
    created(){

        this.returnAll();
    },
    
}
</script>


