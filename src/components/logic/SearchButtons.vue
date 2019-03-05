<template>
    <div id="search-btns" class="game-search-form buttons-carousel">
        <ul class="buttons-carousel__list">

            <li class="buttons-carousel__list-item">
                        <button id="filter-btn-all" class="filter-btn" @click="$emit('filter','abc')">A - Z</button>
            </li>
    
            <li class="buttons-carousel__list-item">
                        <button id="filter-btn-jackpot" class="filter-btn" @click="$emit('filter','jackpot')">Jackpot</button>
            </li>

            <li class="buttons-carousel__list-item">
                        <button id="filter-btn-race" class="filter-btn" @click="$emit('filter','race')">Race games</button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "SearchButtons"
}
</script>

