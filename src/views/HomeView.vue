<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import {computed, onMounted, ref} from "vue";
import HelloWorld from "@/components/HelloWorld.vue";


const productCategory = ref('category 1');

const handleChangeProductCategory = (value) => {
  productCategory.value = value;
}

// computed trả lại 1 value và cache data
const filteredProducts = computed(() => {
  return products.value.filter(item => item.category === productCategory.value);
})

const toDos = ref([]);

// sau khi chạy hết từ trên xuống dưới, chạy hết template thì onMounted() chạy
onMounted(() => {
  fetch('https://jsonplaceholder.typicode.com/todos')
      .then(response => response.json())
      .then(json => toDos.value = json)
  console.log('mounted render');
})

const helloWorld = ref(true);

</script>

<template>
  <main>
    <div v-if="helloWorld">
      <hello-world msg="Hello Vue 3 + Vite" />
    </div>
    <button @click="helloWorld = false">Remove Hello World Component</button>
  </main>
</template>
