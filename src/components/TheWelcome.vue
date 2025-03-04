<script setup>
import {reactive, ref} from "vue";

const object = {
  name: 'John Doe',
  age: 30
}

// ref là một reactive variable
// ref sử dụng 1 đối tượng và 1 thuộc tính
// truy cập thuộc tính ref bằng .value
const count1 = ref(0);

count1.value = count1.value + 1;
count1.value = count1.value + 2;
count1.value = count1.value + 3;

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
  <h1> Welcome {{ object.name }} {{ object.age }} </h1>
  <h1>This is a count2: {{ count2.author }}</h1>

</template>

<style scoped>
h1 {
  color: red
}
</style>
