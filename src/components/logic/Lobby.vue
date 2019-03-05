<template>
    <div id="lobby-all" class="lobby-all" >
        <div id="category-container" class="category-container">

            <SearchContainer v-bind:filtered="filtered"/>


            <CategoryContainer v-on:show-footer="$emit('show-footer')" v-if="false"/>
    

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
    data(){
        return{
            filtered: []
        }
    },
    methods: {
        returnAll(){
            
            for(let i = 0; i < this.$options.myJson.length; i++){   

                this.filtered.push(this.$options.myJson[i]);    

            }
               
        }
    },
    created(){
        this.returnAll();
    }
}
</script>


