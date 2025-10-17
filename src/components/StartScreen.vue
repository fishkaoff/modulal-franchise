<template>
  <div class="start">
    <div class="text">
      <h2 class="title">
        Запустите <span>свое</span> производство грязезащитных решеток по
        <span>нашей</span> технологии
      </h2>

      <ul class="benefits">
        <li class="benefit">
          <img :src="BenefitIcon" class="icon" />
          <p class="text">Низкая конкуренция</p>
        </li>
        <li class="benefit">
          <img :src="BenefitIcon" class="icon" />
          <p class="text">Быстрый старт</p>
        </li>
        <li class="benefit">
          <img :src="BenefitIcon" class="icon" />
          <p class="text">Поддержка на всех этапах</p>
        </li>
      </ul>

      <div class="btns">
        <button class="btn filled-btn">
          <div class="wrapper">
            <span>\1</span> <br />
            Рассчитать стартовые затраты
          </div>
        </button>
        <button class="btn bordered-btn">
          <div class="wrapper">
            <span>\2</span> <br />
            Скачать презентацию
          </div>
        </button>
      </div>
    </div>

    <div class="image">
      <img :src="StartImage" alt="" class="start-image" />
    </div>
  </div>
</template>

<script setup lang="ts">
import StartImage from '@/assets/images/start-picture.png'
import BenefitIcon from '@/assets/images/benefit-icon.svg'
</script>

<style scoped lang="scss">
.start {
  @include mixins.container;
  padding-top: 50px;

  display: flex;
  justify-content: space-between;
  gap: 32px;

  padding-bottom: 100px;

  .text {
    .title {
      @include mixins.main-typo(42px, 500);
      line-height: 1.7em;
      text-transform: uppercase;

      span {
        color: variables.$color-accent-dark;
      }
    }

    .benefits {
      padding-top: 35px;

      .benefit {
        display: flex;

        .icon {
          width: 27px;
          height: auto;
        }

        .text {
          @include mixins.main-typo(32px, 200);
          padding-left: 20px;
        }
      }

      .benefit:not(:first-of-type) {
        padding-top: 18px;
      }
    }

    .btns {
      margin-top: 40px;
      display: flex;
      justify-content: space-between;
      gap: 32px;

      .btn {
        outline: none;
        border: none;
        border-radius: 20px;
        @include mixins.main-typo(24px);
        transition: color 0.5s;
        -webkit-transition: background-color 0.5s linear;
        -ms-transition: background-color 0.5s linear;
        transition: background-color 0.5s linear;

        &.filled-btn {
          background-color: variables.$color-accent;
          color: variables.$color-white;

          .wrapper {
            padding: 17px;
            text-align: left;

            span {
              @include mixins.fun-typo(48px);
            }
          }
        }

        &.filled-btn:hover {
          cursor: pointer;
          background-color: variables.$color-white;
          color: variables.$color-accent;
          border: 1px solid variables.$color-accent;
        }

        &.bordered-btn {
          border: 1px solid variables.$color-accent;
          background-color: variables.$color-white;
          color: variables.$color-accent;

          .wrapper {
            padding: 17px;
            text-align: left;

            span {
              @include mixins.fun-typo(48px);
            }
          }
        }

        &.bordered-btn:hover {
          cursor: pointer;
          border: none;
          background-color: variables.$color-accent;
          color: variables.$color-white;
        }
      }
    }
  }
}
</style>
