<template>
    <div class="pokemonIdCardContainer">
        <div v-for="pokemon in pokemons" :key="pokemon.id" class="pokemonIdCard">
            {{ pokemon.name }}
        </div>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';

// eslint-disable-next-line no-unused-vars
const props = defineProps({
    pokemons: {
        type: Array,
        required: true
    }
});

</script>

<style scoped>
.pokemonIdCard {
    border: 1px solid black;
    border-radius: 5px;
    padding: 10px;
    margin: 10px;
    width: 100px;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.pokemonIdCardContainer {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}
</style>