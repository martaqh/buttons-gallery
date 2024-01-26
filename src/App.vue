<script setup lang="ts">
import { ref } from "vue";
import BaseButton from "@/components/BaseButton.vue";

const isDisplayBlock = ref(false);

const handleDisplayChange = () => {
  isDisplayBlock.value = true;
};
</script>

<template>
  <main class="app">
    <div class="app__buttons-display">
      <div
        class="app__buttons-container"
        :class="{ 'display-block': isDisplayBlock }"
      >
        <BaseButton
          color="yellow"
          size="large"
          @display-block="handleDisplayChange"
        >
          <i class="material-icons">key</i>
          Open me if you can
        </BaseButton>
        <BaseButton
          href="http://www.risify.pl"
          color="green"
          full-width
          @display-block="handleDisplayChange"
        >
          <i class="material-icons">home</i>
          Welcome home
        </BaseButton>
        <BaseButton
          to="About"
          color="red"
          size="small"
          @display-block="handleDisplayChange"
        >
          <i class="material-icons">refresh</i>
          Try again
        </BaseButton>
      </div>
    </div>
  </main>
</template>

<style scoped>
.app {
  height: 100vh;
  background-color: #fce5cd;
}
.app__buttons-display {
  padding: 24px;
  margin: auto;
  position: absolute;
  inset: 0px;
  height: 50vh;
  width: fit-content;
  min-width: 50vw;
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
.app__buttons-container.display-block {
  flex-direction: column;
}
</style>
