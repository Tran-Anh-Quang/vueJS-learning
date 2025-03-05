<script setup>
import { ref } from "vue";
import HelloWorld from "@/components/HelloWorld.vue";

const showHelloWorld = ref(true);

</script>

<template>
  <main>
    <hello-world msg="Hello Vue 3 + Vite" />
  </main>
</template>
