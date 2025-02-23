<script setup>

</script>

<template>
  <div class="slidev-layout mj-layout-section h-full">
    <div class="content-wrapper h-full">
      <div class="left-bar"></div>
      <div class="content">
        <slot/>
      </div>
    </div>
  </div>
</template>

<style scoped>
.mj-layout-section{
  padding: var(--mj-content-padding);
  position: relative;

  .content-wrapper{
    display: flex;
    flex-flow: row nowrap;

    .left-bar{
      height: 100%;
      width: var(--mj-content-padding);
      background: var(--mj-primary-secondary-gradient);
      border-radius: var(--mj-border-radius);
      margin-right: var(--mj-content-padding);
      flex-shrink: 0;
    }

    .content{
      display: flex;
      flex-flow: column nowrap;
      flex-grow: 1;
    }
  }
}
</style>
