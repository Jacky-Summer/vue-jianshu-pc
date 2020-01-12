<template>
    <div class="advertisement">
        <router-link 
            to='/' 
            class="download-container"             
            @mouseenter.native="showQrcode"
            @mouseleave.native="hideQrcode"
        > 
            <img class="qrcode" src="https://cdn2.jianshu.io/assets/web/download-index-side-qrcode-cb13fc9106a478795f8d10f9f632fccf.png" alt="">
            <div class="info">
                <div class="title">下载简书手机App<i class="iconfont icon-link">&#xe61c;</i></div>
                <div class="description">随时随地发现和创作内容</div>
            </div>
        </router-link>
        <div class="popover-container" v-show="isShow">
            <div class="pop-qrcode">
                <img src="https://cdn2.jianshu.io/assets/web/download-index-side-qrcode-cb13fc9106a478795f8d10f9f632fccf.png">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Advertisement',
    data() {
        return {
            isShow: false
        }
    },
    methods: {
        showQrcode() {
            console.log(555)
            this.isShow = true
        },
        hideQrcode() {
            this.isShow = false
        }
    }
}
</script>

<style lang="stylus" scoped>
.advertisement
    position relative
    .download-container
        display block
        margin-bottom 30px
        padding 10px 22px
        width 100%
        border 1px solid #f0f0f0
        border-radius 6px
        background-color #fff
        box-sizing border-box
        .qrcode
            width 60px
            height 60px
            opacity .85
        .info
            display inline-block
            vertical-align middle
            margin-left 7px
            .title
                font-size 15px
                color #333
                .icon-link
                    font-size 13px
            .description
                margin-top 10px
                font-size 13px
                color #999
    .popover-container
        position absolute
        top -184px
        left 50px
        padding 12px 10px
        background #fff
        border-radius 6px
        border 1px solid #2f2f2f
        .pop-qrcode
            position relative
            img 
                height 150px
                width 150px
            &:before
                content ''
                position absolute
                bottom -22px
                left 50%
                margin-left -10px
                border-bottom 0
                border-top 10px solid #999
                border-left 10px solid transparent
                border-right 10px solid transparent
            &:after
                content ''
                position absolute
                bottom -21px
                left 50%
                margin-left -10px
                border-bottom 0 
                border-top 10px solid #fff
                border-left 10px solid transparent
                border-right 10px solid transparent

    
</style>