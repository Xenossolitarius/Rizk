<template>
    <div id="all-content" class="all-content " style="top: 0px;">

    <MobileNav />
    <InsiderTicker />

    <SearchBar />
    <SearchButtons />


    <Footer />

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


export default {
    name: "AllContent",
    components: {
        MobileNav,
        InsiderTicker,
        Footer,
        SearchBar,
        SearchButtons
    }
}
</script>

