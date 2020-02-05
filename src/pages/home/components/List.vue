<template>
    <div class="list-wrapper">
        <div class="banner-wrapper">
            <a href="#">
                <img class="banner-img" src="http://upload.jianshu.io/admin_banners/web_images/4318/60781ff21df1d1b03f5f8459e4a1983c009175a5.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/1250/h/540" alt="">
            </a>
        </div>
        <div class="list-container">
            <ul>
                <li class="list-item" v-for="article in articleList" :key="article.object.data.id">
                    <router-link 
                        :to="'/detail/' + article.object.data.slug"
                        class="wrap-img have-img" 
                        v-if="article.object.data.list_image_url"
                    >
                        <img :src="article.object.data.list_image_url" alt="">
                    </router-link>
                    <div class="content" :class="{ 'have-img': article.object.data.list_image_url }">
                        <router-link :to="'/detail/' + article.object.data.slug" class="title">{{ article.object.data.title }}</router-link>
                        <p class="abstract">{{ article.object.data.public_abbr }}</p>
                        <div class="meta">
                            <span class="reward"><i class="iconfont icon-diamond">&#xe63d;</i> {{ article.object.data.total_rewards_count }}</span>
                            <router-link to='/'><span class="nickname">{{ article.object.data.user.nickname }}</span></router-link>
                            <router-link to='/'><i class="iconfont icon-comment">&#xe684;</i> {{ article.object.data.public_comments_count }}</router-link>
                            <span><i class="iconfont icon-like">&#xe630;</i> {{ article.object.data.likes_count }}</span>
                        </div>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'List',
    props: {
        articleList: Array
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl';
.list-wrapper
    margin-left 18px
    .banner-img
        cursor pointer
        width 625px
        height 270px
        margin-bottom 35px
.list-container
    .list-item 
        position: relative
        width 100%
        margin 0 0 15px
        padding 15px 2px 20px 0
        border-bottom 1px solid #f0f0f0
        box-sizing border-box
        .wrap-img
            &.have-img  
                width 150px
                position: absolute
                top 50%
                margin-top -60px
                right 0
                height 100px
                img 
                    width 100%
                    height 100%
                    border-radius 4px
                    border 1px solid #f0f0f0
        .content
            &.have-img
                padding-right 165px
            .title
                margin -7px 0 4px
                font-size 18px
                font-weight 700
                line-height 1.5
                color #333
            .abstract
                margin 5px 0 8px
                font-size 13px
                line-height 24px
                color #999
            .meta
                font-size 12px
                font-weight 400
                line-height 20px
                span,
                a
                    margin-right 10px
                    color #b4b4b4
                .reward
                    color $orangeColor
                    .icon-diamond
                        font-size 12px
                .icon-comment,
                .icon-like
                    font-size 14px

</style>