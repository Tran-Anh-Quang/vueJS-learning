<script setup>

import {useRoute, useRouter} from "vue-router";

const router = useRouter();

const route = useRoute();

console.log('path', route.path);
console.log('path', route.name);

</script>
<template>
  <div class="about">
    cach 1
    <button @click="router.push({name: 'user'})">about user</button>
    cach 2
    <router-link to="/about/user">about user</router-link>
    <router-view></router-view>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
