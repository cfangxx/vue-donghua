<template>
  <div>
    <transition
      name="fade"
      @before-enter="handleBeforeEnter"
      @enter ="handleEnter"
      @after-enter ="handleAfterEnter"
      @before-leave="handleBeforeLeave"
      @leave ="handleLeave"
      @after-leave ="handleAfterLeave"
    >
      <div v-show="show">Velocity</div>
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
    document.title = 'Vue中JS动画与Velocity.js的结合'
  },
  methods: {
    clickToggle () {
      this.show = !this.show
    },
    handleBeforeEnter (el) {
      el.style.opacity = 0
    },
    handleEnter (el, done) {
      // eslint-disable-next-line
      Velocity(el, {opacity: 1}, {duration: 1000, complete: done})
    },
    handleAfterEnter (el) {
      console.log('入场动画完成')
    },
    handleBeforeLeave (el) {
      el.style.opacity = 1
    },
    handleLeave (el, done) {
      // eslint-disable-next-line
      Velocity(el, {opacity: 0}, {duration: 1000, complete: done})
    },
    handleAfterLeave (el) {
      console.log('出场动画完成')
    }
  }
}
</script>

<style scoped>
div{
  display: inline-block;
}

</style>
