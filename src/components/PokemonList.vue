<template>
    <div>
        <PokemonListRender :pokemons="pokemons" />
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import PokemonListRender from './PokemonListRender.vue';

const pokemons = ref([]);

const fetchPokemons = async () => {
    try {
        const response = await fetch('https://pokeapi.co/api/v2/pokemon');
        const data = await response.json();
        pokemons.value = data.results;
    } catch (error) {
        console.error('Error fetching Pokémon data:', error);
    }
};

onMounted(fetchPokemons);
</script>