<template>
  <div class="home">
    <start-screen />
    <section-title>Зачем это <span>рынку</span></section-title>
    <market-need-screen />

    <section-title>Win-Win</section-title>
    <win-screen></win-screen>
  </div>
</template>

<script setup lang="ts">
import StartScreen from '@/components/StartScreen.vue'
import SectionTitle from '@/components/SectionTitle.vue'
import MarketNeedScreen from '@/components/MarketNeedScreen.vue'
import WinScreen from '@/components/WinScreen.vue'
</script>

<style scoped lang="scss"></style>
