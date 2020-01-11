<template>
  <div class="search-wrapper">
        <input 
            type="text" 
            placeholder="搜索" 
            class="search-input" 
            :class="{focused: focused}"
            @focus="focusInput" 
            @blur="blurInput"
        >
      <a href="#" class="search-btn" :class="{focused: focused}">
          <i class="icon-search iconfont" :class="{focused: focused}">&#xe613;</i>
      </a>
  </div>
</template>

<script>
export default {
    name: 'HeaderSearch',
    data () {
        return {
            focused: false
        }
    },
    methods: {
        focusInput() {
            this.focused = true
        },
        blurInput() {   
            this.focused = false
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
.search-wrapper
    float left
    margin-left 15px
    position relative
    top 8px
    .search-input
        box-sizing border-box
        padding 0 40px 0 20px
        width 240px
        height 38px
        font-size 14px
        border 1px solid #eee
        border-radius 40px
        background #eee
        transition all .4s ease-out
        &.focused
            width 320px
    .search-btn
        position absolute
        top 4px
        right 5px
        width 30px
        height 30px
        color #969696
        text-align: center
        &.focused
            border-radius 50%
            background #969696
        .icon-search
            margin 7px -1px 0 0
            display block
            &.focused
                color #fff

</style>