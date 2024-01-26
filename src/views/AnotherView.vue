<script setup lang="ts">
import ContentDisplay from "@/components/ContentDisplay.vue";
import BaseView from "./BaseView.vue";
import BaseButton from "@/components/BaseButton.vue";
</script>

<template>
  <BaseView>
    <ContentDisplay class="another-view">
      <h1 class="another-view__title">Here you can see some other variants</h1>
      <BaseButton color="orange" full-width>
        <i class="material-icons">star</i>
        I take a full width of my parent
      </BaseButton>
      <BaseButton to="/" color="dark-green" disabled>
        I am disabled
      </BaseButton>
      <BaseButton to="/" size="large" color="green" full-width>
        We all will get you back home
        <i class="material-icons">home</i>
      </BaseButton>
    </ContentDisplay>
  </BaseView>
</template>

<style scoped>
.another-view {
  flex-direction: column;
  justify-content: space-around;
}
.another-view__title {
  font-size: 24px;
  font-weight: 600;
}
</style>
