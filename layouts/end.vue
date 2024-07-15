<!--
  Usage:
```md
---
```yaml
layout: end
```

<content>
-->

<script setup lang="ts">
import Watermark from "../components/watermark.vue";
import SlidesCurrentNumber from "../components/slides-current-number.vue";
</script>

<template>
  <section class="slidev-layout end">
    <article>
      <header class="end-header">
        <watermark />
        <h2>Thanks!</h2>
      </header>
      <div class="end-content">
        <slot />
      </div>
    </article>
  </section>
  <slides-current-number />
</template>

<style>
.slidev-layout.end {
  padding: 2.5rem 5rem 6rem;

  .end-header {
    align-items: center;
    display: flex;
    justify-content: flex-start;
    margin-bottom: 40px;
  }

  .end-content {
    margin: 0.5rem 0.5rem 0.5rem 7.5rem;
  }

  h2 {
    font-size: 7rem;
    font-weight: 600;
    margin: 30px 0;
  }

  .watermark .waterfall {
    width: 5rem;
    margin-right: 30px;
  }
}
</style>
