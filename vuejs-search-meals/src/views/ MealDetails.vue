<template>
    <div>
        <img :src="" alt="/">
    </div>


     
</template>

<script setup>

import {ref, onMounted} from 'vue'
import {useRoute} from 'vue-router';

    const route = useRoute();
    const meal =ref({})

    onMounted(() => {
        route.params.id
    })
</script>