 <template>
    <div class="flex flex-col p-8">
        
            <input type= "text" class="rounded border-2 border-gray-200 w-full"
         placeholder="Search for meals"/>
        
        
    
    <div class="flex justify-center gap-2 mt-2">
        <router-link :to="{name: 'byletter', params:{letter}}" v-for="letter of letters" :key="letter">
            {{ letter }}
        </router-link>
    </div>
</div>
    
 </template>
 
 <script setup>
 import { computed,onMounted } from 'vue';
 import store from '../store';
 import axiosCient from '../axiosClient.js';

 const letters ="ABCDEFGHIJKLMNOPQRSTUVWXYZ".split('');

 onMounted(async () =>{
     const response = await axiosCient.get('list.php?i=list')
     console.log(response.data)
 })
</script> 