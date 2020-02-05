<template>
  <div class="detail">
    <div class="detail-left">
      <Content></Content>
      <Comment></Comment>
    </div>
    <div class="detail-right">
      <AuthorInfo></AuthorInfo>
      <Recommend></Recommend>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Content from './components/Content'
import Comment from './components/Comment'
import AuthorInfo from './components/AuthorInfo'
import Recommend from './components/Recommend'
export default {
    name: 'Detail',
    data() {
      return {
        article: Object
      }
    },
    components: {
      Content,
      Comment,
      AuthorInfo,
      Recommend
    },
    methods: {
      getDetailInfo() {
        axios.get('/detail/asimov/p/' + this.$route.params.slug)
          .then(res => {
            if(res.status === 200) {
              this.article = res.data
              console.log(this.article)
            }
          })
      }
    },
    created() {
      this.getDetailInfo()
    },
    mounted() {
      document.body.style.backgroundColor = "#f9f9f9";
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.detail
  overflow hidden
  padding-top 66px
  container()
  .detail-left
    float left
    width 725px
    margin-left 15px
  .detail-right
    float right
    width 240px
    height 620px
     

</style>