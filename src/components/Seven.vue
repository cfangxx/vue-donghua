<template>
  <div class="one">
    <Opac :show="show">
      <div>渐隐</div>
    </Opac>
    <button @click="clickToggle">Toggle</button>
  </div>
</template>

<script>
import Opac from './SevenTemplate'

export default {
  data () {
    return {
      show: true
    }
  },
  mounted () {
    document.title = 'Vue中的动画封装'
  },
  components: {
    Opac
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
</style>
