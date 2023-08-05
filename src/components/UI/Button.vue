<script setup>
const props = defineProps({
  background: {
    type: String,
    required: false
  },
  type: {
    type: String,
    default: 'button'
  },
  to: {
    type: String,
    required: false
  },
  color: {
    type: String,
    default: 'primary'
  },
  mobileFullWidth: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <button v-if="type==='button'"
          :class="['btn', {'btn--primary': color==='primary','btn--secondary': color==='secondary','btn--lightgray': color==='lightgray', 'btn--fullwidth': mobileFullWidth}]">
    <slot></slot>
  </button>
  <router-link :to="to" v-else
               :class="['btn', {'btn--primary': color==='primary','btn--secondary': color==='secondary','btn--lightgray': color==='lightgray'}]">
    <slot></slot>
  </router-link>
</template>

<style scoped lang="scss">
.btn {
  background: var(--primary);
  color: #fff;
  padding: 0 32px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  border: none;
  font-size: 16px;
  height: 56px;
  text-decoration: none;
  white-space: nowrap;
  @media (max-width: 768px){
    padding: 0 15px;
  }
  &:hover {
    opacity: .8;
  }

  &--primary {
    background: var(--primary);
    color: #fff;
  }

  &--secondary {
    background: rgba(249, 249, 249, 0.15);
    color: #ffffff;
  }

  &--lightgray {
    background: #F9F9F9;
    color: var(--primary);
  }

  &--white {
    background: #ffffff;
    color: var(--primary);
  }
  &--fullwidth{
    @media (max-width: 768px) {
      width: 100%;
    }
  }
}
</style>