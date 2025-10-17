<template>
  <div class="header">
    <div class="wrapper">
      <h1 class="logo">ModulAl.ru</h1>

      <ul class="nav">
        <li v-for="item in navItems">
          <a :href="item.link" class="nav-item">{{ item.text }}</a>
        </li>
      </ul>

      <button class="profile-btn">
        <img :src="ProfileIcon" alt="Личный кабинет" title="Личный кабинет" class="icon" />
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import type { NavItem } from '@/models/nav'
import ProfileIcon from '@/assets/images/profile.svg'

const navItems: NavItem[] = [
  {
    text: 'Зачем это рынку',
    link: '#',
  },
  {
    text: 'Потенциал',
    link: '#',
  },
  {
    text: 'Почему мы',
    link: '#',
  },
  {
    text: 'Примерка бизнес-модели',
    link: '#',
  },
]
</script>

<style scoped lang="scss">
.header {
  -webkit-box-shadow: 0px 5px 8px 0px rgba(34, 60, 80, 0.2);
  -moz-box-shadow: 0px 5px 8px 0px rgba(34, 60, 80, 0.2);
  box-shadow: 0px 5px 8px 0px rgba(34, 60, 80, 0.2);

  .wrapper {
    @include mixins.container;

    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 40px 0 40px 0;

    .logo {
      @include mixins.main-typo(40px, 600);
    }

    .nav {
      display: flex;

      .nav-item {
        @include mixins.main-typo(22px);
        color: variables.$color-black;
        padding-left: 100px;
        transition: all 0.5s;
      }

      .nav-item:hover {
        color: variables.$color-accent;
      }
    }

    .profile-btn {
      border: none;
      outline: none;
      background-color: variables.$color-white;

      .icon {
        width: 35px;
        height: auto;
      }
    }

    .profile-btn:hover {
      cursor: pointer;
    }
  }
}
</style>
