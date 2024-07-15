<!--
  Usage:
```md
---
```yaml
layout: fact
```

<content>
-->
<script setup lang="ts">
import SlidesCurrentNumber from "../components/slides-current-number.vue";
</script>

<template>
  <div class="slidev-layout fact">
    <div>
      <slot />
    </div>
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.fact {
  > div {
    margin-top: auto;
    margin-bottom: auto;
  }
}
</style>
