<script setup>
// Giá trị của defineProps là tên sau ':' ở component cha
const props = defineProps(['count'])

</script>

<template>
  <div> Count: {{ props.count }} </div>
</template>

<style scoped>
</style>
