<script setup lang="ts">
import { computed } from "vue";

type Size = "small" | "regular" | "large";
type Color = "orange" | "green" | "dark-green" | "red" | "yellow";
type ButtonType = "button" | "submit" | "reset";

interface Props {
  to?: string;
  href?: string;
  size?: Size;
  color?: Color;
  type: ButtonType;
  outlined?: boolean;
  disabled?: boolean;
  fullWidth?: boolean;
}

const props = withDefaults(defineProps<Props>(), {
  size: "regular",
  color: "yellow",
  type: "button",
});

const componentVariant = computed(() => {
  if (props.to) {
    return "router-link";
  } else if (props.href) {
    return "a";
  } else {
    return "button";
  }
});

const buttonType = computed(() => {
  return !props.href && !props.to ? props.type : null;
});

const textColor = computed(() => {
  return props.color === "yellow" ? "dark-green" : "white";
});

const focusColor = computed(() => {
  return props.outlined ? "dark-green" : props.color;
});
</script>

<template>
  <component
    class="base-button"
    :is="componentVariant"
    :href="href || to"
    :to="to"
    :type="buttonType"
    :disabled="disabled"
    :class="{
      disabled: disabled,
      outlined: outlined,
      [size]: size,
      'full-width': fullWidth,
    }"
  >
    <div class="base-button__slot">
      <slot>
        <!-- fallback content -->
        Click me
      </slot>
    </div>
  </component>
</template>

<style scoped>
.base-button {
  padding: 14px 24px;
  border-radius: 24px;
  background-color: v-bind("`var(--${color})`");
  color: v-bind("`var(--${textColor})`");
  font-size: 16px;
  font-weight: 600;
  line-height: 125%;
  letter-spacing: -0.48px;
  border: none;

  &:hover {
    background-color: v-bind("`var(--${color}-hover`");
    cursor: pointer;
  }
  &:focus {
    outline: 2px solid v-bind("`var(--${focusColor}`");
  }
}

.outlined {
  background-color: var(--white);
  outline: 1px solid var(--dark-green);
  color: var(--dark-green);

  &:hover {
    background-color: var(--light-green);
  }
}

.disabled {
  opacity: 0.4;
  pointer-events: none;
}

.small {
  padding: 10px 16px;
  font-size: 14px;
  font-weight: 500;
  line-height: 140%;
  letter-spacing: -0.42px;
  border-radius: 20px;
}

.large {
  padding: 16px 24px;
  font-size: 18px;
  font-weight: 600;
  line-height: 135%;
  letter-spacing: -0.54px;
  border-radius: 28px;
}

.full-width {
  width: 100%;
}

.base-button__slot {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  height: 20px;
  white-space: nowrap;

  .small & {
    gap: 4px;
  }

  .large & {
    gap: 10px;
    height: 24px;
  }
}
</style>
