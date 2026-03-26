<template>
  <main>
    <Beverage :isIced="store.currentTemp === 'Cold'" />

    <ul class="option-row">
      <li v-for="temp in store.temps" :key="temp" class="align-item">
        <label><input type="radio" :value="temp" v-model="store.currentTemp" /> {{ temp }}</label>
      </li>
    </ul>

    <ul class="option-row">
      <li v-for="base in store.allBases" :key="base.id" class="align-item">
        <label><input type="radio" :value="base" v-model="store.currentBase" /> {{ base.name }}</label>
      </li>
    </ul>

    <ul class="option-row">
      <li v-for="syrup in store.allSyrups" :key="syrup.id" class="align-item">
        <label><input type="radio" :value="syrup" v-model="store.currentSyrup" /> {{ syrup.name }}</label>
      </li>
    </ul>

    <ul class="option-row">
      <li v-for="creamer in store.allCreamers" :key="creamer.id" class="align-item">
        <label><input type="radio" :value="creamer" v-model="store.currentCreamer" /> {{ creamer.name }}</label>
      </li>
    </ul>

    <div class="make-beverage-controls">
      <input v-model="store.beverageName" placeholder="Beverage Name" />
      <button @click="store.makeBeverage">🍺 Make Beverage</button>
    </div>

    <div id="beverage-container">
      <div v-for="(bev, index) in store.savedBeverages" :key="index">
        <label>
          <input type="radio" name="saved-list" @change="store.showBeverage(bev)" />
          {{ bev.name }}
        </label>
      </div>
    </div>
  </main>
</template>
