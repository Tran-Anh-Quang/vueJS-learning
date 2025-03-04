<script setup>
import {reactive, ref} from "vue";

const textInput = ref('');

</script>

<template>
  <div>
    Text is: {{ textInput }}
  </div>
  <input type="text" v-model.trim="textInput">
</template>

<style scoped>
h1 {
  color: red
}
</style>
