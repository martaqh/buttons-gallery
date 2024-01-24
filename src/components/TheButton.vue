<script setup lang="ts">
import { computed } from "vue";

type Size = "small" | "regular" | "large";
type Variant = "filled" | "outlined";
type Color = "orange" | "green" | "dark-green" | "red" | "yellow";

interface Props {
  to?: string;
  href?: string;
  size: Size;
  variant: Variant;
  color: Color;
}

const props = withDefaults(defineProps<Props>(), {
  size: "regular",
  variant: "filled",
  color: "yellow",
});

const buttonType = computed(() => {
  if (props.to) {
    return "router-link";
  } else if (props.href) {
    return "a";
  } else {
    return "button";
  }
});

const buttonSize = computed(() => {
  if (props.to) {
    return "router-link";
  } else if (props.href) {
    return "a";
  } else {
    return "button";
  }
});

const textColor = computed(() => {
  return props.color === "yellow" ? "dark-green" : "white";
});
</script>

<template>
  <component class="button" :is="buttonType" :href="href" :to="to">
    <slot class="slot"> Click me </slot>
  </component>
</template>

<style scoped>
.button {
  padding: 24px 14px;
  height: fit-content;
  border-radius: 24px;
  background-color: v-bind("`var(--${color})`");
  color: v-bind("`var(--${textColor})`");
  font-size: 16px;
  font-weight: 600;
  font-family: Montserrat;
  line-height: 125%;
  letter-spacing: -0.48px;
  border: none;

  &:hover {
    background-color: v-bind("`var(--${color}-hover`");
  }
  &:focus {
    border: 2px solid v-bind("`var(--${color}-hover`");
  }
}

.slot {
  display: flex;
}
</style>
