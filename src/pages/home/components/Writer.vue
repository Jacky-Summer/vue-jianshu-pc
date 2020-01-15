<template>
    <div class="writer-wrapper">
        <span class="title">推荐作者</span>
        <div class="page-change" @click="changePage"><i class="iconfont icon-rotate" id="change">&#xe851;</i> 换一批</div>
        <ul 
            class="writer-list"
            v-for="item in list"
            :key="item.id"
        >
            <li class="list-item">
                <router-link to='/' class="avatar"><img :src="item.avatar_source" alt=""></router-link>
                <router-link to='/' class="follow"><i class="iconfont icon-follow">&#xe620;</i>关注</router-link>
                <router-link to='/' class="name">{{ item.nickname }}</router-link>
                <p>写了{{ item.total_wordage }}字 · {{ item.total_likes_count }}喜欢</p>
            </li>
        </ul>
    </div>
</template>

<script>

export default {
    name: 'Writer',
    props: {
        list: Array
    },
    data() {
        return {
            rotate: 0
        }
    },
    methods: {
        changePage() {
            let icon = document.getElementById('change')
            this.rotate += 360
            icon.style.transform = 'rotate(' + this.rotate + 'deg)'
        }
    }
}
</script>

<style lang="stylus" scoped>
.writer-wrapper
    .title
        font-size 14px
        color #969696
    .page-change
        float right
        display inline-block
        font-size 14px
        color #969696
        cursor pointer
        .icon-rotate
            display inline-block
            font-size 15px
            transition all .2s ease-in
    .writer-list
        .list-item
            margin-top 18px
            line-height 20px
            .avatar
                float left
                width 48px
                height 48px
                margin-right 10px
                cursor pointer
                img 
                    width 100%
                    height 100%
                    border 1px solid #ddd
                    border-radius 50%
            .follow
                float right
                margin-top 5px
                padding 0
                font-size 13px
                color #42c02e
                .icon-follow
                    font-size 12px
            .name
                padding-top 5px
                margin-right 60px
                font-size 14px
                display block
            p
                margin-top 2px
                font-size 12px
                color #969696


</style>