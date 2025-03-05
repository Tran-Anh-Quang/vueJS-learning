<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import {computed, ref} from "vue";

// const count = ref(10);
//
// const handleIncrease = (data) => {
//   count.value = count.value + data.value;
// }

const productCategory = ref('category 1');

// sử dụng ref cho array còn 1 object bên trong là array thì dùng reactive
const products = ref([
  {
    id: 1,
    name: 'Product 1',
    price: 100,
    category: 'category 1'
  },
  {
    id: 2,
    name: 'Product 2',
    price: 200,
    category: 'category 2'
  },
  {
    id: 3,
    name: 'Product 3',
    price: 300,
    category: 'category 1'
  },
  {
    id: 4,
    name: 'Product 4',
    price: 400,
    category: 'category 2'
  }
])

const handleChangeProductCategory = (value) => {
  productCategory.value = value;
}

// computed trả lại 1 value và cache data
const filteredProducts = computed(() => {
  return products.value.filter(item => item.category === productCategory.value);
})

</script>

<template>
  <main>
<!--    <TheWelcome :count="count" @handle-increase="handleIncrease"/>-->

    <button @click="handleChangeProductCategory('category 1')">Category 1</button>
    <button @click="handleChangeProductCategory('category 2')">Category 2</button>

    <div v-if="productCategory === 'category 1'">List product of category 1</div>
    <div v-else-if="productCategory === 'category 2'">List product of category 2</div>

    <div v-for="product in filteredProducts">
      <div class="group-product-item">
        <div>{{ product.name }}</div>
        <div>{{ product.price }}</div>
      </div>
    </div>
  </main>
</template>
