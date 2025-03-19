<template>
  <div class="syrupLayer" :style="{ backgroundColor: syrupColors[currentSyrup] }"></div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps<{ currentSyrup: string }>();

const syrupColors: Record<string, string> = {
  "No Syrup": "transparent",
  "Vanilla": "#f3e5ab",  // Light vanilla color
  "Caramel": "#c78a47",  // Caramel color
  "Hazelnut": "#b36d3b", // Hazelnut color
};
</script>
<style lang="scss" scoped>

.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
