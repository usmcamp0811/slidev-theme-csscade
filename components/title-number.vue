<script setup lang="ts">
import C from "./c.vue";

defineProps({
  index: {
    type: String,
    default: "1",
  },
});
</script>

<template>
  <aside class="title-number">
    <c></c>
    <div class="title-index">{{ index }}</div>
  </aside>
</template>

<style scoped>
.title-number {
  left: 10%;
  position: absolute;
  width: 60px;

  .title-index {
    font-family: var(--font-secondary);
    font-size: 2rem;
    left: 48%;
    position: absolute;
    top: 15%;
  }
}
</style>
