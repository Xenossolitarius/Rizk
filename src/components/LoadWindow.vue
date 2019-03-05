<template>
    <div id="all-content" class="all-content " style="top: 0px;">

    <MobileNav />
    <InsiderTicker />

    <SearchBar />
    <SearchButtons />
    <CategoryContainer v-on:show-footer="showFooter" />

    <Footer v-if="footerIsShown"/>

    </div>
</template>

<script>
//layouts
import MobileNav from './layouts/MobileNav.vue'
import InsiderTicker from './layouts/InsiderTicker.vue'
import Footer from './layouts/Footer.vue'

//logic
import SearchBar from './logic/SearchBar.vue'
import SearchButtons from './logic/SearchButtons.vue'
import CategoryContainer from './logic/CategoryContainer'


export default {
    name: "LoadWindow",
    data(){
        return {
            footerIsShown: false
        }
    },
    components: {
        MobileNav,
        InsiderTicker,
        Footer,
        SearchBar,
        SearchButtons,
        CategoryContainer
    },
    methods: {
        showFooter(){
            this.footerIsShown = true;
        }

    }
}
</script>

