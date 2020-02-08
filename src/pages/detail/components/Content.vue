<template>
    <div class="detail-content">
        <h1 class="title">{{ article.public_title }}</h1>
        <div class="article-info-wrapper">
            <div class="article-info-container" v-if="article.user">
                <router-link to='/'>
                    <img class="avatar"  :src="article.user.avatar" alt="">
                </router-link>
                <div>
                    <div class="author-info">
                        <span class="nickname"><router-link to='/'>{{ article.user.nickname }}</router-link></span>
                        <button class="btn-follow">关注</button>
                    </div>  
                    <div class="article-info">
                        <span>{{ article.first_shared_at }}</span>
                        <span>字数 {{ article.wordage }}</span>
                    </div>
                </div>
            </div>
            <div class="content" v-html="article.free_content"></div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Content',
    props: {
        article: Object
    },
    data() {
        return {

        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
@import '~styles/variables.styl'
.detail-content
    padding 24px
    color $articleText
    detail-aside()
    .title
        font-size 30px
        font-weight 700
        line-height 42px
        word-break break-word
    .article-info-wrapper
        font-size 13px
        margin 18px 0 32px 0
        .article-info-container
            display flex
            align-items center
            .avatar
                margin-right 8px
                avatar-img()
            .author-info
                display flex
                align-items center
                margin-bottom 6px
                .nickname
                    font-size 16px
                    font-weight 500
                    margin-right 8px
                    a
                        color $articleText
                .btn-follow
                    font-size 12px
                    padding 2px 9px
                    color $orangeColor
                    border-radius 50px
                    background-color #fff
                    border 1px solid $orangeColor
                    cursor pointer
            .article-info
                span
                    margin-right 10px
                    font-size 13px
                    color $smallText
        .content
            font-weight 400
            line-height 1.8
            margin-bottom 20px
            padding 10px 0        
                
    
</style>