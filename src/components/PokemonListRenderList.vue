<template>
    <component :is="suitableComponentBasedOnViewMode"></component>
    <ul>
        <li v-for="pokemon in pokemons" :key="pokemon.id">
            {{ pokemon.name }}
        </li>
    </ul>
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