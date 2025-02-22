<script setup>
</script>

<template>
<div class="slidev-layout layout-two-col h-full">
  <div class="a">
    <h1>{{ $frontmatter.title }}</h1>
    <div class="cols">
      <slot></slot>
    </div>
  </div>
</div>
</template>

<style scoped>
.slidev-layout {
  padding: 16px;
}
h1{
  text-align: center;
  font-family: var(--mj-font-family-title);
  @apply text-2xl;
}

.a{
  display: flex;
  flex-flow: column;
  height: 100%;

  & > * {
    flex: none;
  }

  & > .cols {
    flex: 1;
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
    gap: 32px;
  }
}
.layout-two-col{
 position: relative;
}
</style>

<style>
.layout-two-col .cols > * {
  width: 450px;
}
</style>
