<!--
  Usage:
```md
---
```yaml
layout: intro
```

Quote text

Author name
-->
<script setup lang="ts">
import SlidesCurrentNumber from "../components/slides-current-number.vue";
import WavesBg from "../components/waves-bg.vue";
</script>

<template>
  <section class="slidev-layout quote">
    <slot />
  </section>
  <slides-current-number />
  <waves-bg />
</template>

<style>
.slidev-layout.quote {
  padding: 7.5rem 16rem 6rem;
  text-align: center;

  p {
    font-family: var(--font-primary);
    font-size: 1.5rem;
    font-weight: 600;
    line-height: 2.5rem;
    margin: auto;
    position: relative;
    width: 70%;

    &:last-child {
      font-family: var(--font-secondary);
      font-size: 1.2rem;
      text-align: right;
    }

    &:first-child {
      font-style: italic;
      font-weight: 400;
      text-align: left;

      &::before {
        content: '"';
        font-family: var(--font-secondary);
        font-size: 6rem;
        font-style: normal;
        left: -50px;
        position: absolute;
        top: 30px;
      }
    }
  }
}
</style>
