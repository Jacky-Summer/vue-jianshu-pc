<template>
  <div class="detail-content">
      文章内容
  </div>
</template>

<script>
export default {
    name: 'Content',
    data() {
        return {

        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.detail-content
    padding 24px
    detail-aside()
    
</style>