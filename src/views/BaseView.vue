<template>
  <main class="base-view">
    <slot></slot>
  </main>
</template>

<style scoped>
@keyframes transitionIn {
  from {
    opacity: 0;
    transition: rotateX(-10deg);
  }
  to {
    opacity: 1;
    transition: rotateX(0);
  }
}
.base-view {
  height: 100vh;
  background-color: var(--color-background);
  animation: transitionIn 1.5s;
}
</style>
