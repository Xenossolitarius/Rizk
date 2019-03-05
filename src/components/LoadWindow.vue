<template>
    <div id="all-content" class="all-content " style="top: 0px;">

    <MobileNav />
    <InsiderTicker />

    <SearchBar />
    <SearchButtons v-on:filter="buttonPress"/>

    <Lobby v-on:show-footer="showFooter" v-bind:filter="filter" />

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
import Lobby from './logic/Lobby'


export default {
    name: "LoadWindow",
    data(){
        return {
            footerIsShown: false,
        
            filter: ''
        }
    },
    components: {
        MobileNav,
        InsiderTicker,
        Footer,
        SearchBar,
        SearchButtons,
        Lobby
        
    },
    methods: {
        showFooter(){
            this.footerIsShown = true;
        },
        buttonPress(filter){
           this.filter = filter;
        }


    }
}
</script>

