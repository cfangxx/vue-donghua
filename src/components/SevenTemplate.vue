<template>
  <transition name="opac">
    <slot v-if="show"></slot>
  </transition>
</template>

<script>
export default {
  props: ['show']
}
</script>

<style scoped>
.opac-enter,.opac-leave-to{
  opacity: 0;
}
.opac-enter-active,.opac-leave-active{
  transition: opacity .3s;
}
</style>
