<script setup>
import { onMounted, ref } from 'vue';
import PocketBase from 'pocketbase';

const pb = new PocketBase('http://127.0.0.1:8090');
const titleVal = ref("");
const data = ref([]);



async function submit() {
  
  const record = {
    Title: titleVal.value,
    Description: "desc",
};
  await pb.collection("Shien_Factory").create(record);
  data.value.push(record);
};



</script>

<template>
<p>test</p>
<input  class="bg-gray-700 mx-5 my-5" v-model="titleVal"><br>
<button @click="submit" class="px-5 py-2 bg-pink-300 hover:bg-violet-700 mx-5 my-5">submit</button>


  

</template>
