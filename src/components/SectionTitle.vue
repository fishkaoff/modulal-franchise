<template>
  <div class="section-title">
    <p class="text">
      <slot></slot>
    </p>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.section-title {
  -webkit-box-shadow: 0px 2px 8px 0px rgba(34, 60, 80, 0.2);
  -moz-box-shadow: 0px 2px 8px 0px rgba(34, 60, 80, 0.2);
  box-shadow: 0px 2px 8px 0px rgba(34, 60, 80, 0.2);
  display: flex;
  align-items: center;

  .text {
    @include mixins.container;
    @include mixins.main-typo(40px, 500);
    padding: 65px;

    :deep(span) {
      color: variables.$color-accent-blue;
    }
  }
}
</style>
