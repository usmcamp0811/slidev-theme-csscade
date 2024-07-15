<template>
  <div class="slide-current-number">
    <SlideCurrentNo />
  </div>
</template>

<style scoped>
.slide-current-number {
  align-items: center;
  background-color: #fff;
  border-radius: 50%;
  bottom: 30px;
  color: var(--background-dark);
  display: flex;
  font-size: 0.8rem;
  font-weight: 600;
  height: 50px;
  justify-content: center;
  position: absolute;
  right: 30px;
  width: 50px;
  z-index: 1;
}

html.light .slide-current-number {
  background-color: var(--background-dark);
  color: #fff;
}
</style>
