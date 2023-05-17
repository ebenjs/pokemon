<template>
    <h1>Pokémon List {{ viewMode }}
        <button @click="changeViewMode">Change view mode</button>
    </h1>
    <component :is="suitableComponentBasedOnViewMode" :pokemons="pokemons"></component>
</template>

<script setup>
import { computed, ref } from 'vue';
import PokemonListRenderGrid from './PokemonListRenderGrid.vue';
import PokemonListRenderList from './PokemonListRenderList.vue';

const viewMode = ref('list');

// eslint-disable-next-line no-unused-vars
const props = defineProps({
    pokemons: {
        type: Array,
        required: true
    }
});

const suitableComponentBasedOnViewMode = computed(() => {
    if (viewMode.value === 'grid') {
        return PokemonListRenderGrid;
    }

    return PokemonListRenderList;
});

const changeViewMode = () => {
    if (viewMode.value === 'grid') {
        viewMode.value = 'list';
    } else {
        viewMode.value = 'grid';
    }
};

</script>

<style></style>