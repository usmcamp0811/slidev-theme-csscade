<!--
  Usage:
```md
---
```yaml
layout: image
image: /<img-path>
(optional) backgroundSize: default "cover"
```
-->

<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../helpers/layoutHelper";
import SlidesCurrentNumber from "../components/slides-current-number.vue";

const props = defineProps({
  image: {
    type: String,
  },
  backgroundSize: {
    type: String,
    default: "cover",
  },
});

const style = computed(() =>
  handleBackground(props.image, false, props.backgroundSize),
);
</script>

<template>
  <div class="slidev-layout image" :style="style">
    <slot />
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.image {
  height: 100%;
  text-align: center;
  width: 100%;

  p {
    color: #000;
    font-size: 1.8rem;
    text-shadow:
      0 0 1em #fff,
      0 0 0.2em #fff;
  }
}
</style>
