<!--
  Usage:
```md
---
```yaml
layout: full
```

<content>
-->
<script setup lang="ts">
import SlidesCurrentNumber from "../components/slides-current-number.vue";
</script>

<template>
  <div class="slidev-layout full">
    <slot />
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.full {
  height: 100%;
  width: 100;

  :slotted {
    height: 100%;
    width: 100;
  }
}
</style>
