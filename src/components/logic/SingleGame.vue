<template>
    <div>
        <div class="hover">
            <a class="btn-play">
                <div class="tri"></div>
            </a>
        </div>
        <a href="https://rizk.com/en/casino/temple-of-treasures-megaways/13595">
            <img class="game-img" v-bind:src="require('../../assets/images/'+ game.img +'.jpg')" width="190" height="190" v-bind:alt="game.desc" style="opacity: 1;">
        </a>
		<a class="readmore"></a>
    </div>
</template>

<script>
export default {
    name:"SingleGame",
    props: ["game"]
}
</script>
