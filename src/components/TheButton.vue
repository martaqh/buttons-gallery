<script setup lang="ts">
defineProps<{
  text?: string;
}>();
</script>

<template>
  <component>{{ text }} </component>
</template>

<style scoped></style>
