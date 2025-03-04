<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import {ref} from "vue";

const count = ref(10);
</script>

<template>
  <main>
    <TheWelcome :count="count" />
  </main>
</template>
