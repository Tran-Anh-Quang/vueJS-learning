<script setup>
import {reactive, ref} from "vue";

// ref là một reactive variable
// ref sử dụng 1 đối tượng và 1 thuộc tính
// truy cập thuộc tính ref bằng .value
const count1 = ref(1);

const increase = () => {
  count1.value++;
}

const submitForm = () => {
  count1.value++;
}

// reactive sử dụng 1 object trong có nhiều đối tượng
const count2= reactive({
  author: 'John Doe',
  title: 'Counter',
  age: 30
})

// truy cập thuộc tính reactive không cần .value, sử dụng trực tiếp thuộc tính có sẵn
console.log(count2.author, count2.title, count2.age + 1)

// để sử dụng reactive cho 1 array thì truyền vào 1 ref
const count3 = reactive(ref([]))

</script>

<template>
  <h1>This is a count1: {{ count1 }}</h1>

  cach 1
  <button v-on:click="increase">
    Increase
  </button>

  cach 2
  <button @click="increase">
    Increase
  </button>

<!--  thêm prevent để tránh bị reload page-->
  <form @submit.prevent="submitForm">
    <button type="submit">
      Increase
    </button>
  </form>

</template>

<style scoped>
h1 {
  color: red
}
</style>
