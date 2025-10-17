<template>
  <div class="market">
    <div class="section-wrapper">
      <div class="cards">
        <div class="card" v-for="card in cardsContent">
          <div class="wrapper">
            <div class="title">
              <img :src="MarketCardIcon" class="icon" />
              <div class="text">{{ card.title }}</div>
            </div>

            <p class="content" v-html="card.content"></p>
          </div>
        </div>
      </div>
      <div class="video"></div>
    </div>

    <button class="close-market-need-btn"><p>Закройте потребность рынка в своем городе</p></button>
  </div>
</template>

<script setup lang="ts">
import MarketCardIcon from '@/assets/images/market-card-icon.svg'
import type { MarketNeedCard } from '@/models/market-need'

const cardsContent: MarketNeedCard[] = [
  {
    title: 'Большой рынок',
    content:
      '<span>6500+</span> отдельно стоящих МКД  в год (примерно 18 тыс подъездов), <span>более 480 тыс.кв.м</span> торговых площадей',
  },
  {
    title: 'Слабо выраженная сезонность',
    content: 'Строят и обновляют <span>круглый год</span>',
  },
  {
    title: 'Преимущество у локальных производств',
    content: 'Производство всегда под <span>индивидуальные размеры</span>',
  },
]
</script>

<style scoped lang="scss">
.market {
  @include mixins.container;
  margin-top: 100px;

  .section-wrapper {
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
            .text {
              @include mixins.main-typo(30px, 500);
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

  .close-market-need-btn {
    transition: all 0.7s;
    display: flex;
    outline: none;
    border: none;

    @include mixins.main-typo(32px, 500);
    background-color: variables.$color-accent-blue;
    color: variables.$color-white;

    padding: 26px 36px;
    border-radius: 20px;

    width: 70%;
    margin: 50px auto;

    p {
      width: 100%;
      text-align: center;
    }
  }

  .close-market-need-btn:hover {
    cursor: pointer;
    background-color: #103aad;
  }

  padding-bottom: 100px;
}
</style>
