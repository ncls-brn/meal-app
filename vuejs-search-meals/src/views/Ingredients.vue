<template>
<div class="p-8">
    <h1 class="text-4xl font-bold mb-5">Ingredients</h1>
   
    <router-link
    :to="{
        name: 'byIngredient',
        params: { ingredient: ingredient.strIngredient },
        //params ingredients not strDescription =>strIngredient but bug in page 
        //find the problem for next step.
    }" 
    v-for="ingredient of ingredients" 
    :key="ingredient.idIngredient"
    class="block bg-white rounded p-3 mb-3 shadow"
    >
        <h3 class="text 2xl font-bold mb-3">{{ ingredient.strIngredient }}</h3>
        <p>{{ ingredient.strDescription }}</p>
</router-link>
    
    
</div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import axiosClient from '../axiosClient';


const ingredients =ref([])

onMounted(()=>{
    axiosClient.get("list.php?i=list").then(({ data }) => {
        ingredients.value = data.meals; 

    })
})
</script> 