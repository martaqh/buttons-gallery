<script setup lang="ts">
import ButtonsDisplay from "@/components/ButtonsDisplay.vue";
import BaseView from "./BaseView.vue";
import BaseButton from "@/components/BaseButton.vue";
</script>

<template>
  <BaseView>
    <ButtonsDisplay class="another-view">
      <template #title>
        One of us decided to display us in a block mode
      </template>
      <template #content>
        <BaseButton color="orange" full-width>
          <i class="material-icons">star</i>
          I take a full width of my parent so I trigger a block mode display
        </BaseButton>
        <BaseButton color="dark-green"> I fit my content </BaseButton>
        <BaseButton to="/" color="green" disabled>
          I should bring you home but I am disabled
        </BaseButton>
        <BaseButton size="small" outlined> I am small and outlined </BaseButton>
        <BaseButton to="/" size="large">
          Go back home
          <i class="material-icons">home</i>
        </BaseButton>
      </template>
    </ButtonsDisplay>
  </BaseView>
</template>

<style scoped></style>
