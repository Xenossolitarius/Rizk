<template>
    <div id="casino-search" class="game-search-form">
        <div class="search-input-container">
            <input v-on:input="debounceInput" id="game-search-input" type="text" placeholder="Search for a game">
        </div>
    </div>
</template>

<script>
import _ from 'lodash'

export default {
    name: "SearchBar",
    methods: {
        debounceInput: _.debounce(function(e){
            this.$emit ('search-input', e.target.value);
        },500)
    }
}
</script>
