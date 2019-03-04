<template>
    <div id="lobby-all" class="lobby-all">
        <div id="category-container" class="category-container">

            <div id="game-categories" class="game-categories" >
                <SingleCategory />
            </div>
            
        </div>
    </div>
</template>

<script>
import SingleCategory from './SingleCategory'


export default {
    name:"CategoryContainer",
    components:{
        SingleCategory
    }
}
</script>

