<script setup lang="ts">
import ButtonsDisplay from "@/components/ButtonsDisplay.vue";
import BaseView from "./BaseView.vue";
import BaseButton from "@/components/BaseButton.vue";
</script>

<template>
  <BaseView>
    <ButtonsDisplay class="another-view">
      <template #title> Here are more variants and options in action </template>
      <template #content>
        <BaseButton color="green" full-width>
          <i class="material-icons">west</i>
          I take a full width of my parent
          <i class="material-icons">east</i>
        </BaseButton>
        <BaseButton color="dark-green" size="large">
          I fit my content
        </BaseButton>
        <BaseButton size="small" outlined> I am small and outlined </BaseButton>
        <BaseButton to="/" disabled>
          I should bring you home but I am disabled
        </BaseButton>
        <BaseButton to="/" color="orange" size="large">
          <i class="material-icons">chevron_right</i>
          <i class="material-icons">home</i>
          <i class="material-icons">chevron_left</i>
        </BaseButton>
      </template>
    </ButtonsDisplay>
  </BaseView>
</template>

<style scoped></style>
