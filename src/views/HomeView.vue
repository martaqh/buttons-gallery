<script setup lang="ts">
import BaseView from "./BaseView.vue";
import BaseButton from "../components/BaseButton.vue";
import ButtonsDisplay from "@/components/ButtonsDisplay.vue";
</script>

<template>
  <BaseView class="home">
    <ButtonsDisplay>
      <template #title>
        Welcome to the buttons gallery. Feel free to click anything!
      </template>
      <template #content>
        <BaseButton color="yellow" size="small">
          <i class="material-icons">rocket</i>
          Click me
        </BaseButton>
        <BaseButton href="http://www.risify.pl" color="green">
          <i class="material-icons">rocket</i>
          Go somewhere outside
        </BaseButton>
        <BaseButton to="/another" color="red" size="large">
          <i class="material-icons">rocket</i>
          See more buttons
          <i class="material-icons">forward</i>
        </BaseButton>
      </template>
    </ButtonsDisplay>
  </BaseView>
</template>

<style scoped></style>
