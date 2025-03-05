<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import {ref} from "vue";

const count = ref(10);

const handleIncrease = (data) => {
  count.value = count.value + data.value;
}

// sử dụng ref cho array còn 1 object bên trong là array thì dùng reactive
const products = ref([
  {
    id: 1,
    name: 'Product 1',
    price: 100
  },
  {
    id: 2,
    name: 'Product 2',
    price: 200
  },
  {
    id: 3,
    name: 'Product 3',
    price: 300
  }
])

</script>

<template>
  <main>
    <TheWelcome :count="count" @handle-increase="handleIncrease"/>

    <div v-for="product in products">
      <div class="group-product-item">
        <div>{{ product.name }}</div>
        <div>{{ product.price }}</div>
      </div>
    </div>
  </main>
</template>
