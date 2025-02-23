<script setup>
defineProps({
  logoPath: String
})
</script>

<template>
<div class="mj-footer-logo">
  <div class="wrapper">
    <div class="bg-squares">
      <div class="square transparent"></div>
      <div class="square transparent"></div>
      <div class="square secondary"></div>
      <div class="square primary"></div>
      <div class="square transparent"></div>
      <div class="square primary"></div>
      <div class="square primary"></div>
      <div class="square secondary"></div>
      <div class="square primary"></div>
      <div class="square secondary"></div>
      <div class="square primary"></div>
      <div class="square primary"></div>
      <div class="square secondary"></div>
      <div class="square primary"></div>
      <div class="square secondary"></div>
      <div class="square primary"></div>
    </div>
    <img class="logo" :src="logoPath" alt="">
  </div>
</div>
</template>

<style scoped>
.mj-footer-logo .wrapper{
  position: relative;

  .bg-squares{
    display: grid;
    grid-template-columns:repeat(4, 1.5rem);
    gap: 0.25rem;

    .square{
      height: 1.5rem;
      width: 1.5rem;
      border-radius: var(--mj-border-radius);

      &.transparent{
        background-color: transparent;
      }

      &.primary{
        background-color: var(--mj-primary);
        opacity: .5;
      }

      &.secondary{
        background-color: var(--mj-secondary);
        opacity: .5;
      }
    }
  }

  .logo{
    height: 3.25rem;
    width: 3.25rem;
    position: absolute;
    transform: translate(50%, 50%);
    bottom: 2.5rem;
    right: 2.5rem;

  }
}
</style>
