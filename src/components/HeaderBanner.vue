<template>
  <div class="header-banner">
    <div class="wrapper">
      <p class="left">Грязезащитные решетки под ключ</p>
      <p class="right">Быстро. Качественно. В вашем городе</p>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.header-banner {
  background-color: variables.$color-accent;
  height: 60px;
  display: flex;
  align-items: center;

  .wrapper {
    @include mixins.container;
    display: flex;
    justify-content: space-between;

    p {
      @include mixins.main-typo(24px);
      color: variables.$color-white;
    }
  }
}
</style>
