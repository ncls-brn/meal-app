<template>
<div class="p-10">
    <input type= "text" 
        v-model = "keyword"
        class="rounded border-2 border-gray-200 w-full"
        placeholder="Search for meals"
        @change="searchMeals"
    />
</div>
</template>

<script setup>

const keyword = ref('');
function searchMeals(){

};


</script> 