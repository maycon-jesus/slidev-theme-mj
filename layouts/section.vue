<script setup>

import FooterLogo from "../components/FooterLogo.vue";
</script>

<template>
  <div class="slidev-layout mj-layout-section h-full">
    <div class="content-wrapper h-full">
      <div class="left-bar"></div>
      <div class="content">
        <slot/>
      </div>
    </div>
    <FooterLogo class="footerLogo" :logo-path="$slidev.themeConfigs.logoPath" v-if="$slidev.themeConfigs.logoPath"/>
  </div>
</template>

<style scoped>
.footerLogo{
  position: absolute;
  right: 0;
  bottom: 0;
}

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
