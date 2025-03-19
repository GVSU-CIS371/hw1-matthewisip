<template>
  <div class="baseBeverage" :style="{ backgroundColor: baseColors[currentBase] }"></div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps<{ currentBase: string }>();

const baseColors: Record<string, string> = {
  "Black Tea": "#a97142",
  "Green Tea": "#c1d66d",
  "Coffee": "#5f3619",
};
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>
