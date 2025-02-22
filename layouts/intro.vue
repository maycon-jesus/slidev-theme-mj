<script setup>
defineProps({
  image: {
    type: String,
    default: 'https://cover.sli.dev'
  },
  author: {
    type: String,
    default: 'Maycon Jesus',
  }
})
</script>

<template>
  <div class="slidev-layout mj-layout-intro h-full mj-theme-dark">
    <div class="img-bg" :style="{backgroundImage: `url(${$frontmatter.background || image})`}"/>
    <div class="content-wrapper h-full">
      <div class="mj-border">
        <div class="content h-full">
          <div class="img-bg-content" :style="{backgroundImage: `url(${$frontmatter.background || image})`}"/>
          <span class="author">{{$frontmatter.author || author}}</span>
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.content-wrapper {
  padding: var(--mj-content-padding);
  color: var(--mj-foreground);

  & > .mj-border{
    background: linear-gradient(to right bottom, var(--mj-primary), var(--mj-secondary));
    height: 100%;
    padding: var(--mj-content-padding-small);
    border-radius: 10px;
    overflow: hidden;

    & .content{
      --sum: var(--mj-content-padding-small) + var(--mj-content-padding);
      background-size: calc(100% + var(--sum)) calc(100% + var(--sum));
      background-position: center center;
      border-radius: 5px;
      position: relative;
      padding: 64px;

      & .author{
        position: absolute;
        right: var(--mj-content-padding-small);
        bottom: var(--mj-content-padding-small);
        color: var(--mj-primary-foreground);
        padding: 0 var(--mj-content-padding-small);
        background: var(--mj-primary-secondary-gradient);
        border-radius: 8px;
      }
    }
  }
}

.slidev-layout{
  position: relative;

  & .img-bg{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-size: 100% 100%;
    background-position: center center;
    filter: grayscale(100%) brightness(0.5);
    z-index: -1;
  }

  & .img-bg-content{
    position: absolute;
    top: 50%;
    left: 50%;
    width: 100%;
    height: 100%;
    transform: translate(-50%, -50%);
    background-size: calc(100% + (var(--mj-content-padding) + var(--mj-content-padding-small)) * 2)  calc(100% + (var(--mj-content-padding) + var(--mj-content-padding-small)) * 2);
    background-position: center center;
    filter: grayscale(100%) brightness(0.5);
    z-index: 0;

    & ~ *{
      z-index: 1;
    }
  }
}
</style>

<style>
.mj-layout-intro .content{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column nowrap;

  & h1{
    @apply text-6xl font-bold text-center;
    font-family: var(--mj-font-family-title);
  }

  & h2{
    margin-top: 20px;
    @apply text-2xl font-semibold text-center;
  }
}
</style>
