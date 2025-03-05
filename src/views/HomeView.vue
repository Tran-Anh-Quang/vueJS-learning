<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import {ref} from "vue";

const count = ref(10);

const handleIncrease = (data) => {
  count.value = count.value + data.value;
}

</script>

<template>
  <main>
    <TheWelcome :count="count" @handle-increase="handleIncrease"/>
  </main>
</template>
