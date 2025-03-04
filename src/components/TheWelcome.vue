<script setup>
const object = {
  name: 'John Doe',
  age: 30
}
</script>

<template>
<h1> Welcome {{ object.name }} {{ object.age }} </h1>
</template>

<style scoped>
h1 {
  color: red
}
</style>
