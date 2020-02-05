<template>
  <div class="author-info">
      作者信息及相关文章
  </div>
</template>

<script>
export default {
    name: 'AuthorInfo',
    data() {
        return {

        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.author-info
    padding 16px
    height 312px
    detail-aside()

</style>