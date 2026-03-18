<template>
  <div class="syrup" :style="{ '--syrup-color': currentSyrup.color }"></div>
</template>

<script setup lang="ts">
import { currentSyrup } from "../stores/beverage";
</script>

<style lang="scss" scoped>

/*from assn2*/
@mixin syrup-layer($color) {
  background: repeating-linear-gradient(
    45deg,
    tan,
    tan 10px,
    $color 10px,
    $color 20px
  );
}

.syrup {
  transform: translateY(400%);
  @include syrup-layer(var(--syrup-color, #ffefd5));
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
