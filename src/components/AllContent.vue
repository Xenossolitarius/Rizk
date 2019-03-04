<template>
    <div id="all-content" class="all-content " style="top: 0px;">

    <MobileNav />
    <InsiderTicker />
    

    </div>
</template>

<script>
import MobileNav from './layouts/MobileNav.vue'
import InsiderTicker from './layouts/InsiderTicker.vue'

export default {
    name: "AllContent",
    components: {
        MobileNav,
        InsiderTicker
    }
}
</script>

