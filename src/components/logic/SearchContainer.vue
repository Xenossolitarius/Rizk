<template>

    <div id="games-a-z" class="games-a-z" style="display: block;">
                <h2 class="categoryTitle">All games</h2>
                    <ul class="game-grid search-grid" id="a-z-list">
                         <li v-for="game in filtered" v-bind:key="game.id">                                
                                <SingleGame v-bind:game="game" v-on:change-info="changeInfo"/>                                
                            </li>      
                    </ul>
    </div>

</template>

<script>
import SingleGame from './SingleGame'
export default {
    name:"SearchContainer",
    components: {
        SingleGame
    },
    props: ["filtered"]
}
</script>

