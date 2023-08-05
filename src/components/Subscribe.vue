<script setup>
import UIButton from "@/components/UI/Button.vue";
import SubscribeForm from "@/components/SubscribeForm.vue";
</script>

<template>
  <div class="subscribe">
    <div class="subscribe-content">
      <h3 class="subscribe-title">Join the club and get the benefits</h3>
      <span class="subscribe-description">Sign up for our newsletter and receive exclusive offers on new ranges, sales, pop up stores and more</span>
      <div class="subscribe-checks">
        <div class="subscribe-check">
          <img src="/svg/check.svg" alt="check" class="subscribe-check-icon">
          <span class="subscribe-check-name">Exclusive offers</span>
        </div>
        <div class="subscribe-check">
          <img src="/svg/check.svg" alt="check" class="subscribe-check-icon">
          <span class="subscribe-check-name">Free events</span>
        </div>
        <div class="subscribe-check">
          <img src="/svg/check.svg" alt="check" class="subscribe-check-icon">
          <span class="subscribe-check-name">Large discounts</span>
        </div>
      </div>
      <SubscribeForm/>
    </div>
  </div>
</template>

<style scoped lang="scss">
.subscribe {
  background-image: url('/img/subscribe.png');
  background-size: cover;
  padding: 97px 0 86px;
  @media (max-width: 768px){
    padding: 35px;
    margin: 0 -24px;
    background: url("/img/subscr-mobile.png");
    background-size: cover;
  }
  &-content {
    max-width: 500px;
    margin: auto;
    text-align: center;
    color: #ffffff;
    @media (max-width: 768px){
      text-align: left;
    }
  }

  &-title {
    display: block;
    margin: 0 0 12px 0;
    font-size: 32px;
    @media (max-width: 768px){
      font-size: 24px;
    }
  }

  &-description {
    display: block;
    font-size: 18px;
    margin-bottom: 30px;
    @media (max-width: 768px){
      font-size: 14px;
      margin-bottom: 20px;
    }
  }

  &-checks {
    display: flex;
    justify-content: center;
    gap: 36px;
    margin-bottom: 40px;
    @media (max-width: 768px){
      display: block;
    }
  }

  &-check {
    display: flex;
    align-items: center;
    @media (max-width: 768px){
      margin-bottom: 8px;
    }
    &-icon {
      margin-right: 9px;
    }
  }

  &-form {
    display: flex;

    &__input {
      flex-grow: 1;
    }
  }
}
</style>