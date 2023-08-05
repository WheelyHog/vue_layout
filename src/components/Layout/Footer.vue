<script setup>

import SubscribeForm from "@/components/SubscribeForm.vue";
</script>

<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-top">
        <div class="footer-menu">
          <div class="footer-menu-column">
            <span class="footer-menu-title">Menu</span>
            <router-link to="" class="footer-menu-link">New arrivals</router-link>
            <router-link to="" class="footer-menu-link">Best sellers</router-link>
            <router-link to="" class="footer-menu-link">Recently viewed</router-link>
            <router-link to="" class="footer-menu-link">Popular this week</router-link>
            <router-link to="" class="footer-menu-link">All products</router-link>
          </div>

          <div class="footer-menu-column">
            <span class="footer-menu-title">Categories</span>
            <router-link to="" class="footer-menu-link">Crockery</router-link>
            <router-link to="" class="footer-menu-link">Furniture</router-link>
            <router-link to="" class="footer-menu-link">Homeware</router-link>
            <router-link to="" class="footer-menu-link">Plant pots</router-link>
            <router-link to="" class="footer-menu-link">Chairs</router-link>
            <router-link to="" class="footer-menu-link">Crockery</router-link>
          </div>

          <div class="footer-menu-column">
            <span class="footer-menu-title">Our company</span>
            <router-link to="" class="footer-menu-link">About us</router-link>
            <router-link to="" class="footer-menu-link">Vacancies</router-link>
            <router-link to="" class="footer-menu-link">Contact us</router-link>
            <router-link to="" class="footer-menu-link">Privacy</router-link>
            <router-link to="" class="footer-menu-link">Returns policy</router-link>
          </div>
        </div>
        <div class="footer-subscribe">
          <SubscribeForm colorButton="white" bg-input="rgba(255,255,255, .15)" colorText="#fff"/>
        </div>
      </div>
      <div class="footer-bottom">
        <span class="footer-bottom-copyright">Copyright 2022 Avion LTD</span>
        <div class="footer-bottom-socials">
          <a href="#" class="footer-bottom-socials-link"><img src="/svg/linked.svg" alt=""></a>
          <a href="#" class="footer-bottom-socials-link"><img src="/svg/fb.svg" alt=""></a>
          <a href="#" class="footer-bottom-socials-link"><img src="/svg/insta.svg" alt=""></a>
          <a href="#" class="footer-bottom-socials-link"><img src="/svg/skype.svg" alt=""></a>
          <a href="#" class="footer-bottom-socials-link"><img src="/svg/twitter.svg" alt=""></a>
          <a href="#" class="footer-bottom-socials-link"><img src="/svg/pinterest.svg" alt=""></a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped lang="scss">
.footer {
  background: var(--primary);
  color: #ffffff;
  @media (max-width: 768px) {
    margin: 0 -24px;
  }

  &-content {
    padding: 58px 82px 25px;
    @media (max-width: 1024px) {
      padding: 58px 30px 30px 30px;
    }
    @media (max-width: 768px) {
      padding: 40px 35px;
    }
  }

  &-top {
    display: grid;
    grid-template-columns: 540px 1fr;
    column-gap: 110px;
    border-bottom: 1px solid #4E4D93;
    padding-bottom: 48px;
    @media (max-width: 1150px) {
      column-gap: 10px;
      grid-template-columns: 450px 1fr;
    }
    @media (max-width: 1024px) {
      grid-template-columns: repeat(2, 1fr);
    }
    @media (max-width: 768px) {
      grid-template-columns: 1fr;
    }
  }

  &-menu {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    @media (max-width: 1024px) {
      grid-template-columns: repeat(2, 1fr);
    }

    &-column {
      @media (max-width: 768px) {
        margin-bottom: 40px;
      }
    }

    &-title {
      font-weight: bold;
      margin-bottom: 12px;
      display: block;
    }

    &-link {
      display: block;
      color: #ffffff;
      font-size: 14px;
      text-decoration: none;
      margin-bottom: 12px;

      &:hover {
        text-decoration: underline;
      }
    }
  }

  &-bottom {
    padding-top: 22px;
    display: flex;
    justify-content: space-between;
    @media (max-width: 768px) {
      display: block;
      text-align: center;
    }
    &-copyright {
      font-size: 14px;
      @media (max-width: 768px){
        display: block;
        margin-bottom: 20px;
      }
    }

    &-socials {
      display: flex;
      align-items: center;
      justify-content: center;

      &-link {
        margin: 0 12px;

        &:hover {
          opacity: .8;
        }
      }
    }
  }
}
</style>