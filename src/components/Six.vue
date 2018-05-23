<template>
  <div>
    <transition-group name="fade">
      <div v-for="item of list" :key="item.id">
        {{item.title}}
      </div>
    </transition-group>
    <button @click="handleBtnAdd">Add</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      list: []
    }
  },
  mounted () {
    this.count = 0
    document.title = 'Vue中的列表过渡'
  },
  methods: {
    handleBtnAdd () {
      this.list.push({
        id: this.count++,
        title: 'hello world'
      })
    }
  }
}
</script>

<style scoped>
.fade-enter,.fade-leave-to{
  opacity: 0;
}
.fade-enter-active,.fade-leave-active{
  transition: opacity .3s;
}
</style>
