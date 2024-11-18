<!--
  Usage:
```md
---
```yaml
layout: section
```

## Transition headline

<content>
-->
<script setup lang="ts">
import TitleNumber from "../components/title-number.vue";
import SlidesCurrentNumber from "../components/slides-current-number.vue";
import WavesBg from "../components/waves-bg.vue";

const props = defineProps({
  index: {
    type: String,
    default: "1",
  },
});
</script>

<template>
  <section class="slidev-layout section">
    <header class="section-header">
      <title-number :index="index" />
      <slot />
    </header>
  </section>
  <slides-current-number />
  <waves-bg />
</template>

<style>
.slidev-layout.section {
  padding: 10rem 6rem 6rem;
  text-align: center;

  .section-header {
    align-items: flex-start;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    text-align: left;
  }

  h2 {
    font-size: 3rem;
    line-height: 4rem;
    margin-left: 6rem;
  }

  p {
    margin: 0.5rem 0.5rem 0.5rem 6rem;
  }
}
</style>
