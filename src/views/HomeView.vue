<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import {computed, onMounted, ref, watch, watchEffect} from "vue";
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

const showHelloWorld = ref(true);

// watch sẽ theo dõi ref và chạy khi ref thay đổi
// ở đây ref chính là showHelloWorld
watch([showHelloWorld, toDos], (newValue, oldValue) => {
  console.log('new value', newValue);
  console.log('old value', oldValue);
})

// không truyền tham số như watch, theo dõi toàn bộ value
watchEffect(() => {
  console.log('showHelloWorld', showHelloWorld.value);
  console.log('toDos', toDos.value);
})

</script>

<template>
  <main>
    <div v-if="showHelloWorld">
      <hello-world msg="Hello Vue 3 + Vite" />
    </div>
    <button @click="showHelloWorld = !showHelloWorld">Remove Hello World Component</button>
  </main>
</template>
