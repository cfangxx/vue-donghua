<template>
  <div class="one">
    <transition name="opac">
      <div v-show="show">渐隐</div>
    </transition>
    <button @click="clickToggle">Toggle</button>
  </div>
</template>

<script>
export default {
  name: 'One',
  data () {
    return {
      show: true
    }
  },
  mounted () {
    document.title = 'Css过渡动画'
  },
  methods: {
    clickToggle () {
      this.show = !this.show
    }
  }
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
