<template>
  <div>
    <!-- type = "transition"： 动画时长以transition为准 -->
    <!--  :duration="5000" 自定义动画播放时长 -->
    <!--  :duration="{enter: 3000, leave: 5000}" 分别自定义进出场动画播放时长 -->
    <transition name="fade"
      :duration="{enter: 1000, leave: 5000}"
      appear
      enter-active-class="animated swing fade-enter-active"
      leave-active-class="animated shake fade-leave-active"
      appear-active-class="animated swing"
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
    document.title = 'Vue中同时使用过渡和动画'
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
.fade-enter,.fade-leave-to{
  opacity: 0;
}
.fade-enter-active,.fade-leave-active{
  transition: opacity 3s;
}

</style>
