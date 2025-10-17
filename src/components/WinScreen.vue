<template>
  <div class="win">
    <h2 class="section-title">
      <span>Снижайте</span> затраты ваших клиентов и делайте среду безопасней
      <span>вместе с нами</span>
    </h2>

    <div class="section-wrapper">
      <div class="cards">
        <div class="card" v-for="card in cardsContent">
          <div class="wrapper">
            <div class="title">
              <img :src="card.icon" class="icon" />
              <div class="text">{{ card.title }}</div>
            </div>

            <p class="content" v-html="card.content"></p>
          </div>
        </div>
      </div>
      <div class="video"></div>
    </div>
  </div>
</template>

<script setup lang="ts">
import MarketCardIcon from '@/assets/images/market-card-icon.svg'
import type { WinCard } from '@/models/win-card'

import CleanIcon from '@/assets/images/clean.svg'
import LockIcon from '@/assets/images/lock.svg'
import StoncksIcon from '@/assets/images/stoncks.svg'

const cardsContent: WinCard[] = [
  {
    icon: CleanIcon,
    title: 'Экономия на клининге',
    content:
      '<span>Меньше грязи</span> заносится с обувью посетителей = <span>меньше затраты</span> на уборку',
  },
  {
    icon: LockIcon,
    title: 'Безопасность на входных зонах',
    content: 'Значительное <span>снижение риска</span> травм на скользких покрытиях ',
  },
  {
    icon: StoncksIcon,
    title: 'Увеличение трафика',
    content:
      '<span>Чистое помещение</span> = аккуратное, качественное, безопасное – <span>выше трафик</span>',
  },
]
</script>

<style scoped lang="scss">
.win {
  @include mixins.container;
  margin-top: 100px;

  .section-title {
    @include mixins.main-typo(40px, 500);
    color: variables.$color-black;
    line-height: 1.5em;
    text-align: center;
    text-transform: uppercase;

    span {
      color: variables.$color-accent;
    }
  }

  .section-wrapper {
    padding-top: 100px;
    display: flex;
    justify-content: space-between;
    gap: 70px;

    .cards {
      .card {
        -webkit-box-shadow: 0px 2px 8px 7px rgba(34, 60, 80, 0.2);
        -moz-box-shadow: 0px 2px 8px 7px rgba(34, 60, 80, 0.2);
        box-shadow: 0px 2px 8px 7px rgba(34, 60, 80, 0.2);
        border-radius: 20px;

        .wrapper {
          padding: 25px;

          .title {
            display: flex;
            align-items: center;
            .text {
              @include mixins.main-typo(30px, 600);
              padding-left: 10px;
            }
          }

          .content {
            @include mixins.main-typo(27px);
            line-height: 1.5em;
            margin-top: 25px;

            :deep(span) {
              color: variables.$color-accent-blue;
            }
          }
        }
      }

      .card:not(:first-of-type) {
        margin-top: 36px;
      }
    }

    .video {
      width: 100%;
      height: auto;
      border-radius: 20px;
      background-color: #ccc;
    }
  }

  padding-bottom: 100px;
}
</style>
