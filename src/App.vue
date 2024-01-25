<script setup lang="ts">
import BaseButton from "@/components/BaseButton.vue";
</script>

<template>
  <main class="app">
    <div class="app__buttons-container">
      <BaseButton color="dark-green"> </BaseButton>
      <BaseButton href="http://www.risify.pl" color="green" disabled>
      </BaseButton>
      <BaseButton to="About" color="red"> </BaseButton>
    </div>
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
  border-radius: 24px;
  background-color: white;
}
.app__buttons-container {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 24px;
  background-color: inherit;
}
</style>
