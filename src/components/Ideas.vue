<script setup>
import HeroInformation from "@/components/HeroInformation.vue";
</script>

<template>
  <div class="ideas">
      <HeroInformation
          title="It started with a small idea"
          description="A global brand with local beginnings, our story begain in a small studio in South London in early 2014"
          link="#"
          background="var(--primary)"
          colorTitle="#fff"
          colorDescription="#fff"
          :mobilePadding="true"

      />
      <img src="/img/room.png" alt="room" class="ideas-image">
    </div>
</template>

<style scoped lang="scss">
.ideas{
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  column-gap: 16px;
  padding: 0 80px;
  margin-bottom: 60px;
  @media (max-width: 768px) {
    grid-template-columns: 1fr;
    padding: 0;
  }
&-image{
  height: 100%;
  object-fit: cover;
  @media (max-width: 768px) {
    margin-top: 24px;
    height:auto ;
  }
}
}
</style>