<template>
    <div id="search-btns" class="game-search-form buttons-carousel">
        <ul class="buttons-carousel__list">
            <li class="buttons-carousel__list-item">
                        <button id="filter-btn-all" class="filter-btn">A - Z</button>
            </li>
            <li class="buttons-carousel__list-item">
                        <button id="filter-btn-provider" class="filter-btn">Providers</button>
            </li>
            <li class="buttons-carousel__list-item">
                        <button id="filter-btn-jackpot" class="filter-btn">Jackpot</button>
            </li>
            <li class="buttons-carousel__list-item">
                        <button id="filter-btn-race" class="filter-btn">Race games</button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "SearchButtons"
}
</script>

