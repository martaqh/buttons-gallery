<script setup lang="ts">
import { ref } from "vue";
import BaseView from "./BaseView.vue";
import BaseButton from "../components/BaseButton.vue";
import ContentDisplay from "@/components/ContentDisplay.vue";

const isDisplayBlock = ref(false);

const handleDisplayChange = () => {
  isDisplayBlock.value = true;
};
</script>

<template>
  <BaseView class="home">
    <ContentDisplay>
      <div
        class="home__buttons-container"
        :class="{ 'display-block': isDisplayBlock }"
      >
        <BaseButton color="yellow" size="small">
          I am an ordinary button
        </BaseButton>
        <BaseButton href="http://www.risify.pl" color="green" outlined>
          <i class="material-icons">rocket</i>
          Go somewhere outside
        </BaseButton>
        <BaseButton to="/example" color="red" size="large">
          See some more buttons
          <i class="material-icons">forward</i>
        </BaseButton>
      </div>
    </ContentDisplay>
  </BaseView>
</template>

<style scoped>
.home__buttons-container {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 24px;
  background-color: inherit;
}
.home__buttons-container.display-block {
  flex-direction: column;
}
</style>
