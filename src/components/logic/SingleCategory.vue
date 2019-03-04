<template>
    <div class="cat">
        <h2 class="categoryTitle" id="title-1">{{category[0].cat}}</h2>
            <div class="category-desktop" id="category-2">
                <div class="navi-arrow navi-arrow-left"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                    <div class="navi-arrow navi-arrow-right"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                        <ul class="categoryRow categoryRowDesktop clearfix" id="categoryrow-1">
                            <li v-for="game in category" v-bind:key="game.id">
                                <SingleGame v-bind:game="game"/>
                            </li>
                        </ul>
            </div>
    </div>
         
</template>

<script>
import SingleGame from './SingleGame'

export default {
    name:"SingleCategory",
    components:{
        SingleGame
    },
    props: ["category"]
}
</script>

