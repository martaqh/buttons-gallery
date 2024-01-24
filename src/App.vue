<script setup lang="ts">
import TheButton from "@/components/TheButton.vue";
</script>

<template>
  <main class="app">
    <TheButton href="http://www.risify.pl" color="dark-green"> </TheButton>
  </main>
</template>

<style scoped>
.app {
  padding: 24px;
  margin: auto;
  position: absolute;
  inset: 0px;
  width: 70vw;
  height: 50vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
