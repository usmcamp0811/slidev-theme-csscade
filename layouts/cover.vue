<!--
  Usage:
```md
---
```yaml
layout: intro
(optional) org: Organisation name
(optional) animatedBackground: false
```

<div class="subtitle">Csscade</div>

# This is your presentation title

01/01/2024
-->

<script setup lang="ts">
import WaterfallBg from "../components/waterfall-bg.vue";

defineProps({
  animatedBackground: {
    type: Boolean,
    default: true,
  },
  org: {
    type: String,
    default: "Csscade",
  },
});
</script>

<template>
  <section class="slidev-layout cover">
    <article>
      <div class="org">{{ org }}</div>
      <slot />
    </article>
  </section>
  <waterfall-bg :animated="animatedBackground" />
</template>

<style>
.slidev-layout.cover {
  padding: 2.5rem 5rem 6rem;
  position: relative;
  width: 100%;

  .watermark {
    left: 15px;
    position: absolute;
    top: 15px;
  }
}
</style>
