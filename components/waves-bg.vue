<script setup lang="ts">
defineProps({
  animated: {
    type: Boolean,
    default: true,
  },
});
</script>

<template>
  <aside class="waves-bg" :class="{ animated: animated }">
    <div class="waves">
      <svg class="editorial" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
        viewBox="0 24 150 28" preserveAspectRatio="none">
        <defs>
          <path id="gentle-wave" d="M-160 44c30 0
    58-18 88-18s
    58 18 88 18
    58-18 88-18
    58 18 88 18
    v44h-352z" />
        </defs>
        <g class="parallax">
          <use xlink:href="#gentle-wave" x="50" y="0" />
          <use xlink:href="#gentle-wave" x="50" y="3" />
          <use xlink:href="#gentle-wave" x="50" y="6" />
        </g>
      </svg>
    </div>
  </aside>
</template>

<style scoped lang="scss">
@use "sass:color";

.waves-bg {
  position: fixed;
  bottom: -40px;
  left: 0;
  width: 100%;

  .editorial {
    display: block;
    width: 100%;
    height: 10em;
    max-height: 100vh;
    margin: 0;
  }

  .parallax>use {
    animation: move-forever 40s linear infinite;

    $primary-color: #59b7d4;

    &:nth-child(1) {
      animation-delay: -2s;
      fill: color.adjust($primary-color, $lightness: 18%);
    }

    &:nth-child(2) {
      animation-delay: -2s;
      animation-duration: 20s;
      fill: $primary-color;
    }

    &:nth-child(3) {
      animation-delay: -4s;
      animation-duration: 12s;
      fill: color.adjust($primary-color, $lightness: -18%);
    }
  }

  @keyframes move-forever {
    0% {
      transform: translate(-90px, 0%);
    }

    100% {
      transform: translate(85px, 0%);
    }
  }
}
</style>

<!--Edited from Andy Fitzsimon -->

<!--Copyright (c) 2024 by Andy Fitzsimon (https://codepen.io/andyfitz/pen/aZrKdV)-->

<!--Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:-->

<!--The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.-->

<!--THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.-->
