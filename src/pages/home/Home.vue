<template>
  <div class="container">
    <div class="home-left">
      <List :articleList="articleList"></List>
    </div>
    <div class="home-right">
      <Recommend :list="recommendList"></Recommend>
      <Advertisement></Advertisement>
      <Writer></Writer>
    </div>
  </div>
</template>

<script>
import List from './components/List'
import Recommend from './components/Recommend'
import Writer from './components/Writer'
import Advertisement from './components/Advertisement'
import axios from 'axios'
export default {
  name: 'Home',
  data () {
    return {
      articleList: [],
      recommendList: []
    }
  },
  components: {
    List,
    Recommend,
    Writer,
    Advertisement
  },
  methods: {
    getArticle() {
      axios.get('/api/homeList.json')
        .then(res => {
          console.log(res)
          if(res.data && res.data.success) {
            const data = res.data.data
            this.articleList = data.articleList
            this.recommendList = data.recommendList
          }
        })
    }
  },
  created() {
    this.getArticle()
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.container
  margin-top 86px
  container()
  .home-left
    float left
    width 625px
    margin-left 15px
  .home-right
    width 280px
    float right
      

</style>
