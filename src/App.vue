<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <ul class="option-row">
      <li v-for="temp in temps" :key="temp"  class="align-item">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
      </li>
    </ul>
    <ul class="option-row">
      <li v-for="base in bases" :key="base.id" class="align-item">
          <label>
            <input
              type="radio"
              name="bases"
              :id="`b-${base.id}`"
              :value="base"
              v-model="currentBase"
            />
            {{ base.name }}
          </label>
      </li>
    </ul>
    <ul class="option-row">
      <li v-for="syrup in syrups" :key="syrup.id" class="align-item">
          <label>
            <input
              type="radio"
              name="syrups"
              :id="`s-${syrup.id}`"
              :value="syrup"
              v-model="currentSyrup"
            />
            {{ syrup.name }}
          </label>
      </li>
    </ul>
    <ul class="option-row">
      <li v-for="creamer in creamers" :key="creamer.id" class="align-item">
          <label>
            <input
              type="radio"
              name="creamers"
              :id="`c-${creamer.id}`"
              :value="creamer"
              v-model="currentCreamer"
            />
            {{ creamer.name }}
          </label>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp, bases, currentBase, creamers, currentCreamer, syrups, currentSyrup } from "./stores/beverage";
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}

ul {
  list-style: none;
}

.option-row {
  display: flex;
  flex-wrap: wrap;
  padding: 0;
}

.align-item {
  width: 120px;
}

.align-item label {
  display: flex;
  align-items: center;
  gap: 0.35rem;
}
</style>
