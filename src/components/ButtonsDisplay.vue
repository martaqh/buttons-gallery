<template>
  <div class="buttons-display">
    <h1 class="buttons-display__title"><slot name="title"></slot></h1>
    <div class="buttons-display__content">
      <slot name="content"></slot>
    </div>
  </div>
</template>

<style scoped>
.buttons-display {
  background-color: var(--white);
  padding: 48px;
  margin: auto;
  position: absolute;
  inset: 0px;
  height: fit-content;
  width: fit-content;
  min-width: 50vw;
  border-radius: 24px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  gap: 48px;
}

.buttons-display__title {
  font-size: 20px;
  font-weight: 600;
  line-height: 150%;
  text-align: center;
  opacity: 0.8;
}

.buttons-display__content {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 24px;
  background-color: inherit;
}

.buttons-display__content:has(.full-width) {
  flex-direction: column;
}
</style>
