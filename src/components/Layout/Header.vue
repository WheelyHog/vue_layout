<template>
  <header class="header">
    <div class="header-top">
      <div class="header-top-left">
        <div class="header-top-search">
          <img src="/svg/Search.svg" alt="search" class="header-top-icon">
        </div>
        <div class="header-top-mobile-menu" @click=" isopenedMobileMenu = !isopenedMobileMenu">
          <img src="/svg/mob-menu.svg" alt="menu">
        </div>
      </div>

      <router-link to="/" class="header-logo">Avion</router-link>
      <div class="header-top-right">
        <div class="header-top-right__cart">
          <router-link to="/cart">
            <img src="/svg/cart.svg" alt="cart">
            <span class="header-top-right-count" v-if="cartStore.cart.length>0">{{ cartStore.cart.length }}</span>
          </router-link>
        </div>
        <div class="header-top-right__user">
          <router-link to="/user">
            <img src="/svg/avatar.svg" alt="avatar">
          </router-link>
        </div>
      </div>
    </div>
    <div class="header-menu">
      <router-link :to="element.path" v-for="(element, index) of menu" :key="index"
                   class="header-menu__link">{{ element.name }}
      </router-link>
    </div>

    <div class="header-menu-mobile" v-if="isopenedMobileMenu">
      <!--      <div class="header-menu-mobile-top">-->
      <!--        <img src="/svg/mob-menu.svg" alt="menu">-->
      <!--      </div>-->
      <router-link :to="element.path" v-for="(element, index) of menu" :key="index"
                   class="header-menu-mobile-link">{{ element.name }}
      </router-link>
    </div>

  </header>
</template>

<style lang="scss" scoped>
.header {
  height: 132px;
  background: #fff;
  position: relative;
  @media (max-width: 768px) {
    height: auto;
  }

  &-top {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    height: 70px;
    align-items: center;
    border-bottom: 1px solid rgba(0, 0, 0, .1);
    margin: 0 28px;
    @media (max-width: 768px) {
      margin: 0;
      border: none;
      height: 0;
      padding: 20px;
      display: flex;
      justify-content: space-between;
    }

    &-icon {
      display: block;
    }

    &-left {
      display: flex;
      gap: 22px;
      align-items: center;
      @media (max-width: 768px) {
        order: 2;
      }
    }

    &-mobile-menu {
      display: none;
      @media (max-width: 768px) {
        display: block;
      }
    }

    &-search {
      @media (max-width: 768px) {

      }
    }

    &-right {
      display: flex;
      justify-content: flex-end;
      align-items: center;
      gap: 16px;
      @media (max-width: 768px) {
        display: none;
      }

      &__cart {
        position: relative;
      }

      &-count {
        position: absolute;
        width: 15px;
        height: 15px;
        background: #4E4D93;
        border-radius: 50%;
        color: #ffffff;
        font-size: 10px;
        text-decoration: none;
        display: flex;
        justify-content: center;
        align-items: center;
        right: -8px;
        bottom: 0;
      }
    }
  }

  &-logo {
    color: #22202e;
    font-size: 24px;
    text-decoration: none;
    text-align: center;
    @media (max-width: 768px) {
      order: 1;
    }

    &:hover {
      text-decoration: underline;
    }
  }

  &-menu {
    height: 62px;
    display: flex;
    justify-content: center;
    align-items: center;
    @media (max-width: 768px) {
      display: none;
    }

    &__link {
      margin: 0 22px;
      color: var(--gray);
      text-decoration: none;

      &:hover {
        text-decoration: underline;
      }
    }

    &-mobile {
      position: absolute;
      background: #ffffff;
      border: 1px solid black;
      width: 100%;
      padding: 10px;

      &-top {
        display: flex;
        justify-content: flex-end;
        margin-bottom: 24px;
      }

      &-link {
        display: block;
        margin-bottom: 20px;
        color: var(--gray);
        text-decoration: none;
      }

    }

  }

}
</style>

<script setup>
import {ref} from "vue";
import {useCartStore} from "@/store/cart.js";

const cartStore = useCartStore()
console.log(cartStore.cart.length)

const menu = [
  {
    name: 'Plant pots',
    path: '/plant'
  },
  {
    name: 'Ceramics',
    path: '/ceramics'
  },
  {
    name: 'Tables',
    path: '/tables'
  },
  {
    name: 'Chairs',
    path: '/chairs'
  },
  {
    name: 'Crockery',
    path: '/crockery'
  },
  {
    name: 'Tableware',
    path: '/tableware'
  },
  {
    name: 'Cutlery',
    path: '/cutlery'
  },
]
const isopenedMobileMenu = ref(false);
</script>