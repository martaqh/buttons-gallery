<template>
  <div class="content-display">
    <slot></slot>
  </div>
</template>

<style scoped>
.content-display {
  padding: 48px;
  margin: auto;
  position: absolute;
  inset: 0px;
  height: 50vh;
  width: fit-content;
  min-width: 50vw;
  border-radius: 24px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--white);
}
</style>
