<script setup lang="ts">
import Avatar1 from './components/Avatar1.vue';
import Avatar2 from './components/Avatar2.vue';
import Avatar3 from './components/Avatar3.vue';
import Avatar4 from './components/Avatar4.vue';
import { calcChecksum, Random } from "./util/util";
import {IconProps} from './IconProps'
import {ref} from 'vue'

const components = [
  Avatar1,
  Avatar2,
  Avatar3,
  Avatar4
];

// taken from tailwind color pallete: 100
const bgColors = [
  "#fee2e2",
  "#ffedd5",
  "#fef3c7",
  "#fef9c3",
  "#ecfccb",
  "#dcfce7",
  "#d1fae5",
  "#ccfbf1",
];

// taken from tailwind color pallete: 200, 600, 900
const denoColors = [
  ["#fecaca", "#dc2626", "#7f1d1d"],
  ["#d9f99d", "#65a30d", "#365314"],
  ["#a7f3d0", "#059669", "#064e3b"],
  ["#bae6fd", "#0284c7", "#0c4a6e"],
  ["#ddd6fe", "#7c3aed", "#4c1d95"],
];

const component = ref()
component.value = Math.floor(Math.random() * 4);

const bgColorItem = ref()
bgColorItem.value = Math.floor(Math.random() * bgColors.length);

const denoColorItem = ref()
denoColorItem.value = Math.floor(Math.random() * denoColors.length);

function random(){
  component.value = Math.floor(Math.random() * 4);
  bgColorItem.value = Math.floor(Math.random() * bgColors.length);
  denoColorItem.value = Math.floor(Math.random() * denoColors.length);
}
</script>

<template>
<div>
  <div class="card">
    <img class="cord" src="./assets/cord.svg" alt="cord">
    <Avatar1 class="avatar" v-if="component === 0" :bgColor="bgColors[bgColorItem]" :denoColor="denoColors[denoColorItem]" />
    <Avatar2 class="avatar" v-if="component === 1" :bgColor="bgColors[bgColorItem]" :denoColor="denoColors[denoColorItem]" />
    <Avatar3 class="avatar" v-if="component === 2" :bgColor="bgColors[bgColorItem]" :denoColor="denoColors[denoColorItem]" />
    <Avatar4 class="avatar" v-if="component === 3" :bgColor="bgColors[bgColorItem]" :denoColor="denoColors[denoColorItem]" />
    <p>
      <button @click="random()">Get Random</button>
    </p>
    <div>
      <input value="Can generate random cute avatars" type="text" id="url">
    </div>
    
  </div>

  <!-- <img class="logo" src="./assets/logo.svg" alt="Deno Avatar Logo"> -->
  <a href="https://github.com/xiaoxunyao/vue-avatar-lite" class="github-link">
    <img class="github-logo" src="./assets/github.svg" alt="GitHub Repo">
  </a>
</div>
</template>

<style>

</style>
