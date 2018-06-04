<template>
  <transition name="move">
    <div class="food" v-show="showFlag">
      <div class="food-content">
        <div class="image-header">
          <img :src="food.image">
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    food: {
      type: Object
    }
  },
  created() {},
  data() {
    return {
      showFlag: false
    }
  },
  methods: {
    show() {
      this.showFlag = true
    }
  },
  computed: {}
}
</script>

<style lang="stylus" scoped>
.food
  position fixed
  left 0
  top 0
  bottom 48px
  z-index 30
  width 100%
  background #fff
  transform translate3d(0, 0, 0)
  &.move-enter-active, &.move-leave-active
    transition all .3s linear
  &.move-enter, &.move-leave-to
    transform translate3d(100%, 0, 0)
  .image-header
    position relative
    width 100%
    height 0
    padding-top 100% // 图片占位
    img
      position absolute
      top 0
      left 0
      width 100%
      height 100%
 </style>
