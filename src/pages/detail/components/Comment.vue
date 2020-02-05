<template>
  <div class="comment">评论</div>
</template>

<script>
export default {
    name: 'Comment'
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.comment
    padding 16px
    detail-aside()

</style>