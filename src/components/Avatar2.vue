<script lang="ts" setup>
import { toRefs, computed } from "vue";
let props = defineProps({
    bgColor:{
      type: String,
      required: true,
    },
    denoColor: {
      type: String[100],
      required: true,
    }
})
</script>

<template>
    <svg
      width="112"
      height="112"
      viewBox="0 0 112 112"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <g>
        <rect width="112" height="112" :fill="bgColor" />
        <path
          d="M47 85.5C37 97 35.5 112.667 36 122C44.6667 121.333 85.4 124 117 122C115 115.5 109 101.591 99 92.5C89 83.4091 69.5075 79.2671 69.5 79C69.1667 67.1667 67 49.2052 67 42.5C67 30 59 23.5 47 23.5C35 23.5 25.5 30 25.5 40.5C25.5 51.0001 37 56 47 56V85.5Z"
          :fill="denoColor[0]"
          :stroke="denoColor[2]"
          stroke-width="3" />
        <path
          d="M47 56C47.8333 56 49.8 55.8 51 55"
          :stroke="denoColor[1]"
          stroke-opacity="0.51"
          stroke-width="3"
          stroke-linecap="round" />
        <circle cx="45.5" cy="41.5" r="2.5" fill="black" />
        <path
          d="M71.3292 86.3416C72.0701 86.7121 72.9712 86.4118 73.3416 85.6708C73.7121 84.9299 73.4118 84.0288 72.6708 83.6584L71.3292 86.3416ZM68.0062 78.6358C68.0965 79.6295 68.3373 81.1631 68.7805 82.5841C69.002 83.2942 69.2896 84.0274 69.665 84.6654C70.0275 85.2814 70.5572 85.9556 71.3292 86.3416L72.6708 83.6584C72.6428 83.6444 72.4809 83.5353 72.2506 83.144C72.0333 82.7746 71.8272 82.2767 71.6445 81.6909C71.2794 80.5203 71.0702 79.2039 70.9938 78.3642L68.0062 78.6358Z"
          :fill="denoColor[1]"
          fill-opacity="0.5" />
      </g>
    </svg>  
</template>

<style>

</style>
