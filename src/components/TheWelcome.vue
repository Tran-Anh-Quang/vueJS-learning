<script setup>
// Giá trị của defineProps là tên sau ':' ở component cha
const props = defineProps(['count'])
const emit = defineEmits(['handle-increase']);

const onCrease = () => {
  emit('handle-increase', {lable: 'increase', value: 10});
}

</script>

<template>
  <div> Count: {{ props.count }} </div>
  <button @click="onCrease">Increase</button>
</template>

<style scoped>
</style>
