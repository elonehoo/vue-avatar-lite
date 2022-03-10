<script setup lang="ts">
import Avatar1 from './components/Avatar1.vue';
import Avatar2 from './components/Avatar2.vue';
import Avatar3 from './components/Avatar3.vue';
import Avatar4 from './components/Avatar4.vue';
import { calcChecksum, Random } from "./util/util";
import {IconProps} from './IconProps'

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

const now = new Date();
now.setDate(now.getDate() + 14);
const init = {
  headers: [["content-type", "image/svg+xml"], ["Expires", now.toUTCString()], ["Cache-Control", "public, max-age=604800"]],
};

const Icon = (props: IconProps) => {
  if (props.seed === undefined) {
    props.seed = "";
  }
  const checksum = calcChecksum(props.seed);
  const rand = new Random(checksum);
  const bgColor = bgColors[rand.nextInt(0, bgColors.length - 1)];
  const denoColor = denoColors[rand.nextInt(0, denoColors.length - 1)];
  const component = components[rand.nextInt(0, components.length - 1)];

  return (
    component(bgColor, denoColor)
  );
};


</script>

<template>
<div>
  <div class="card">
    <img class="cord" src="./assets/cord.svg" alt="cord">
    <img class="avatar" id="output" src="" alt="avatar" width="150" />
    <p>
      <button onclick="getRandom()">Get Random</button>
    </p>
    <div>
      <input title="Copy URL from here" type="text" id="url">
    </div>
  </div>

  <!-- <img class="logo" src="./assets/logo.svg" alt="Deno Avatar Logo"> -->
  <a href="https://github.com/hashrock/deno-avatar" class="github-link">
    <img class="github-logo" src="./assets/github.svg" alt="GitHub Repo">
  </a>
</div>
</template>

<style>

</style>
