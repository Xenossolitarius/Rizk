<template>
    <div class="cat">
        <h2 class="categoryTitle" id="title-2">Latest Releases</h2>
            <div class="category-desktop" id="category-2">
                <div class="navi-arrow navi-arrow-left"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                    <div class="navi-arrow navi-arrow-right"><img src="../../assets/arrow.svg" alt="Arrow"></div>
                        <ul class="categoryRow categoryRowDesktop clearfix" id="categoryrow-2">
                            <SingleGame />
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
    }
}
</script>

