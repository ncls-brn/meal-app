<template>
<div class="p-10">
    <input type= "text" 
        v-model = "keyword"
        class="rounded border-2 border-gray-200 w-full"
        placeholder="Search for meals"
        @change="searchMeals"
    />
</div>

<pre>{{ meals }}</pre>
</template>

<script setup>
import { ref } from 'vue';
import { computed } from '@vue/reactivity';
import axiosClient from '../axiosClient';
import store from '../store';

const keyword = ref('');
const meals = computed(()=> store.state.searchedMeals)

function searchMeals(){
    store.dispach('searchMeals', keyword.value)
};


</script> 