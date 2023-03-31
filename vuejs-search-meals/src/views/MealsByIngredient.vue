<template>
<Meals :meals="meals"/>

</template>

<script setup>
import { onMounted, ref } from 'vue';
import store from '../store';
import { useRoute } from 'vue-router';
import { computed } from '@vue/reactivity';
import Meals from '../components/Meals.vue'; 

const meals = computed(() => store.state.mealsByIngredient)
const route = useRoute();

onMounted(() => {
    store.dispatch('searchMealsByIngredient', route.params.ingredient)
})
</script>