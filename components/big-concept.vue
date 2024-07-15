<script setup lang="ts">
defineProps({
  slogan: {
    type: String,
    default: "I love CSS",
  },
});
</script>

<template>
  <article class="big-concept">
    <svg
      version="1.1"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      x="0px"
      y="0px"
      style="display: none"
    >
      <symbol id="wave">
        <path
          d="M420,20c21.5-0.4,38.8-2.5,51.1-4.5c13.4-2.2,26.5-5.2,27.3-5.4C514,6.5,518,4.7,528.5,2.7c7.1-1.3,17.9-2.8,31.5-2.7c0,0,0,0,0,0v20H420z"
        ></path>
        <path
          d="M420,20c-21.5-0.4-38.8-2.5-51.1-4.5c-13.4-2.2-26.5-5.2-27.3-5.4C326,6.5,322,4.7,311.5,2.7C304.3,1.4,293.6-0.1,280,0c0,0,0,0,0,0v20H420z"
        ></path>
        <path
          d="M140,20c21.5-0.4,38.8-2.5,51.1-4.5c13.4-2.2,26.5-5.2,27.3-5.4C234,6.5,238,4.7,248.5,2.7c7.1-1.3,17.9-2.8,31.5-2.7c0,0,0,0,0,0v20H140z"
        ></path>
        <path
          d="M140,20c-21.5-0.4-38.8-2.5-51.1-4.5c-13.4-2.2-26.5-5.2-27.3-5.4C46,6.5,42,4.7,31.5,2.7C24.3,1.4,13.6-0.1,0,0c0,0,0,0,0,0l0,20H140z"
        ></path>
      </symbol>
    </svg>
    <div class="box">
      <div class="slogan-wrapper">
        <div class="slogan">
          {{ slogan }}
        </div>
      </div>
      <div id="water" class="water">
        <svg viewBox="0 0 560 20" class="water_wave water_wave_back">
          <use xlink:href="#wave"></use>
        </svg>
        <svg viewBox="0 0 560 20" class="water_wave water_wave_front">
          <use xlink:href="#wave"></use>
        </svg>
      </div>
    </div>
  </article>
</template>

<style scoped lang="scss">
.big-concept {
  align-items: center;
  color: #fff;
  display: flex;
  height: 300px;
  justify-content: center;
  margin: 0 auto 50px;
  padding: 20px 50px;
  width: 350px;

  $waterFColor: darken(#59b7d3, 18%);
  $waterBColor: lighten(#59b7d3, 18%);

  .box {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 280px;
    width: 280px;
    position: absolute;
    border-radius: 100%;
    overflow: hidden;

    .slogan-wrapper {
      align-items: center;
      display: flex;
      justify-content: center;
      height: 100%;
      padding-top: 50px;
      width: 100%;
    }

    .slogan {
      font-family: var(--font-secondary);
      font-size: 2rem;
      line-height: 2rem;
      margin: auto;
      max-width: 80%;
      text-align: center;
      text-transform: uppercase;
      z-index: 1;
    }

    .water {
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      transform: translate(0, 30%);
      background: $waterFColor;
      transition: all 0.6s;

      &_wave {
        width: 200%;
        position: absolute;
        bottom: 100%;

        &_back {
          right: 0;
          fill: $waterBColor;
          animation: wave-back 2.8s infinite linear;
        }

        &_front {
          left: 0;
          fill: $waterFColor;
          margin-bottom: -1px;
          animation: wave-front 1.4s infinite linear;
        }
      }
    }
  }

  @keyframes wave-front {
    100% {
      transform: translate(-50%, 0);
    }
  }

  @keyframes wave-back {
    100% {
      transform: translate(50%, 0);
    }
  }
}
</style>

<!--Edited from Elaine-->

<!--Copyright (c) 2024 by Elaine (https://codepen.io/ElaineXu/pen/jrzGrw) Permission-->
<!--is hereby granted, free of charge, to any person obtaining a copy of this-->
<!--software and associated documentation files (the "Software"), to deal in the-->
<!--Software without restriction, including without limitation the rights to use,-->
<!--copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the-->
<!--Software, and to permit persons to whom the Software is furnished to do so,-->
<!--subject to the following conditions: The above copyright notice and this-->
<!--permission notice shall be included in all copies or substantial portions of the-->
<!--Software. THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,-->
<!--EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF-->
<!--MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO-->
<!--EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR-->
<!--OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING-->
<!--FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN-->
<!--THE SOFTWARE.-->
