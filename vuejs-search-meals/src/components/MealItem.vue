<template>
  <div class="bg-white shadow rounded-xl p-3">
    <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
      <img
        :src="meal.strMealThumb"
        :alt="meal.strMeal"
        class="rounded-t-xl w-full h-48 object-cover"
      />
    </router-link>
    <h3 class="font-bold">{{ meal.strMeal }}</h3>
    <p class="mb-4">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem, dicta
      fuga? Similique, inventore quisquam autem, omnis laborum, est eos magni
      eligendi natus ratione culpa obcaecati quas facere magnam quam. Minima.
    </p>
    <div class="flex items-center justify-between">
      <YouTubeButton :href="meal.strYoutube">YouTube</YouTubeButton>
      <!--<router-link to="/" class="px-3 py-3 rounded border-2 text-white border-blue-600 bg-blue-500 hover:bg-blue-600 hover:transition-colors">
            View
        </router-link>-->
    </div>
  </div>
</template>

<script setup>

const { meal } = defineProps({
  meal: {
    required: true,
    type: Object,
  },
});
</script>
