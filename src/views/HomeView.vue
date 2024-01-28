<script setup lang="ts">
import BaseButton from "@/components/BaseButton.vue";
import ButtonsDisplay from "@/components/ButtonsDisplay.vue";
import BaseView from "@/views/BaseView.vue";
</script>

<template>
  <BaseView class="home-view">
    <ButtonsDisplay>
      <template #title>
        Welcome to a humble buttons gallery. <br />
        Feel free to click any exhibit!
      </template>
      <template #content>
        <BaseButton size="small"> Click to see me focused </BaseButton>
        <BaseButton href="http://www.risify.pl" color="green">
          <i class="material-icons">rocket_launch</i>
          Go to outer spaces
        </BaseButton>
        <BaseButton to="/another" color="red" size="large">
          See more buttons
          <i class="material-icons">forward</i>
        </BaseButton>
      </template>
    </ButtonsDisplay>
  </BaseView>
</template>

<style scoped></style>
