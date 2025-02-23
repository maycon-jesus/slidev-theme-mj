<script setup>
import FooterLogo from "../components/FooterLogo.vue";

const imagePath = $frontmatter.image;
const imageWidth = $slidev.configs.canvasWidth*0.4
</script>

<template>
  <div class="slidev-layout mj-layout-image-left h-full">
    <div class="wrapper h-full">
      <div class="left-bar"></div>
      <img class="layout-img" :src="imagePath" :width="imageWidth" />
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

.slidev-layout{
  position: relative;

  .wrapper{
    display: flex;
    flex-flow: row nowrap;

    .left-bar{
      height: 100%;
      width: var(--mj-content-padding);
      background: var(--mj-primary-secondary-gradient);
      flex: none;
    }

    .layout-img{
      object-fit: cover;
      object-position: center center;
      flex: none;
    }

    .content{
      padding: 0 var(--mj-content-padding);
      flex: 1;
    }
  }
}
</style>
