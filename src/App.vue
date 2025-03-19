<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" :currentBase="currentBase" :currentSyrup="currentSyrup":currentCreamer="currentCreamer" />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
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
        </template>
      </li>
    </ul>
  </div>
  <div>
    <Base :currentBase="currentBase" />
    <ul>
      <li>
        <template v-for="base in baseOptions" :key="base">
          <label>
            <input
              type="radio"
              name="base"
              :id="`r${base}`"
              :value="base"
              v-model="currentBase"
            />
            {{ base }}
          </label>
        </template>
      </li>
    </ul>
  </div>
  <div>
    <Creamer :isCreamer="currentCreamer === 'No Cream'" />
    <ul>
      <li>
        <template v-for="creamer in creamerOptions" :key="creamer">
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`r${creamer}`"
              :value="creamer"
              v-model="currentCreamer"
            />
            {{ creamer }}
          </label>
        </template>
      </li>
    </ul>
  </div>
  <div>
    <Syrup :isSyrup="currentSyrup === 'No Syrup'" />
    <ul>
      <li>
        <template v-for="syrup in syrupOptions" :key="syrup">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${syrup}`"
              :value="syrup"
              v-model="currentSyrup"
            />
            {{ syrup }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";

const baseOptions = ["Black Tea", "Green Tea", "Coffee"];
const creamerOptions = ["No Cream", "Milk", "Cream", "Half & Half"];
const syrupOptions = ["No Syrup", "Vanilla", "Caramel", "Hazelnut"];

const currentBase = ref(baseOptions[0]);
const currentCreamer = ref(creamerOptions[0]);
const currentSyrup = ref(syrupOptions[0]);
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
div {
  margin: 10px 0;
}

input[type="radio"] {
  margin-right: 5px;
}
</style>
