<script setup lang="ts">
import { RouterView } from 'vue-router'
import HeaderBanner from './components/HeaderBanner.vue'
import AppHeader from './components/AppHeader.vue'
</script>

<template>
  <header-banner />
  <app-header />
  <RouterView />
</template>

<style scoped></style>
