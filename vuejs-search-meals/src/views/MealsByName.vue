<template>
<div class="p-10">
    <input type= "text" 
        v-model = "keyword"
        class="rounded border-2 border-gray-200 w-full"
        placeholder="Search for meals"
        @change="searchMeals"
    />
</div>

<div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
    <div v-for="meal of meals" :key="meal.idMeal" class="bg-white shadow rounded-xl">
        <div class="p-3">
            <img :src="meal.strMealThumb" :alt="strMeal" class="rounded-t-xl w-full h-48 object-cover">
        <h3 class="font-bold">{{ meal.strMeal }}</h3>
        <p class="mb-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem, dicta fuga? Similique, inventore quisquam autem, omnis laborum, est eos magni eligendi natus ratione culpa obcaecati quas facere magnam quam. Minima.</p>
        <div class="p-3">
            <a :href="meal.strYoutube" target="_blank" class="px-3 py-3 rounded border-2 border-rose-700 hover:bg-red-600 hover:text-white transition-colors">YouTube</a>
            <router-link to="/" class="px-3 py-3 rounded border-2 border-blue-700 hover:bg-blue-600 hover:text-white transition-colors">
                View
            </router-link>>
    
        </div>

        </div>

    </div>
</div>
</template>

<script setup>
import { ref } from 'vue';
import { computed } from '@vue/reactivity';
import store from '../store';

const keyword = ref('');
const meals = computed(()=> store.state.searchedMeals)

function searchMeals(){
    store.dispatch('searchMeals', keyword.value)
};


</script> 