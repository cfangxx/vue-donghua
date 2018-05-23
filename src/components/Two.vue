<template>
  <div>
    <!-- <transition name="fade" enter-active-class="enter" leave-active-class="leave">
      <div v-show="show">Animate</div>
    </transition> -->
    <!-- appear   appear-active-class="animated zoomIn" 初次出场也执行动画 -->
    <transition name="fade"
      appear
      enter-active-class="animated zoomIn"
      leave-active-class="animated zoomOut"
      appear-active-class="animated zoomIn"
    >
      <div v-show="show">Animate</div>
    </transition>
    <button @click="clickToggle">Toggle</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      show: true
    }
  },
  mounted () {
    document.title = 'Vue中使用Animate.css'
  },
  methods: {
    clickToggle () {
      this.show = !this.show
    }
  }
}
</script>

<style scoped>
div{
  display: inline-block;
}
/* @keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
.enter{
  transform-origin: left center;
  animation: bounce-in 1s;
}
.leave{
  transform-origin: left center;
  animation: bounce-in 1s reverse;
} */

</style>
