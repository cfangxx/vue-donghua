<template>
  <div>
    <!-- mode: 设置多个元素切换时的效果  in-out  out-in-->
    <transition name="fade" mode="out-in">
      <component :is="type"></component>
      <!-- key 阻止Dom复用 -->
      <!-- <div v-if="show" key="hello">Hello</div>
      <div v-else key="bye">Bye</div> -->
    </transition>
    <button @click="clickToggle">Toggle</button>
  </div>
</template>

<script>
import ChildOne from './FiveChildOne'
import ChildTwo from './FiveChildTwo'

export default {
  data () {
    return {
      show: true,
      type: 'ChildOne'
    }
  },
  mounted () {
    document.title = 'Vue中多个元素或组件的过渡'
  },
  methods: {
    clickToggle () {
      // this.show = !this.show
      this.type = this.type === 'ChildOne' ? 'ChildTwo' : 'ChildOne'
    }
  },
  components: {
    ChildOne,
    ChildTwo
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
  transition: opacity .5s;
}

</style>
