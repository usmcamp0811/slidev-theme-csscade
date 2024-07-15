<!--
  Usage:
```md
---
```yaml
layout: center
```

<content>
-->
<script setup lang="ts">
import SlidesCurrentNumber from "../components/slides-current-number.vue";
import WavesBg from "../components/waves-bg.vue";
</script>

<template>
  <div class="slidev-layout center">
    <div>
      <slot />
    </div>
    <slides-current-number />
    <waves-bg />
  </div>
</template>

<style>
.slidev-layout.center {
  display: grid;
  height: 100%;
  place-content: center;
  text-align: center;

  > div {
    margin-bottom: auto;
    margin-top: auto;
  }

  strong {
    font-family: var(--font-secondary);
    font-size: 7rem;
  }
}
</style>
