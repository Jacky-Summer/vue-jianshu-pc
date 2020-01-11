<template>
    <div>
        <nav class="nav-wrapper">
            <div class="width-limit">
                <router-link to='/' class="logo"><img src="../../assets/img/logo.png" alt="简书"></router-link>
                <router-link to='/' class="btn-right"><i class="icon-write iconfont">&#xe60e;</i>写文章</router-link>
                <router-link to='/' class="sign-up">注册</router-link>
                <router-link to='/' class="sign-in">登录</router-link>
                <div class="diamond-wrapper">
                    <router-link to='/' class="diamond">
                        <img src="../../assets/img/diamond.png" alt="" class="img-diamond">
                    </router-link>
                </div>
                <div class="style-mode">
                    <div class="style-mode-btn">
                        <i class="icon-mode iconfont">&#xe636;</i>
                    </div>
                </div>
                <div class="menu-container">
                    <div class="nav-bar">
                        <ul class="navbar-nav">
                            <li class="tab">
                                <router-link to='/' class="tab-item active">
                                    <i class="icon-menu iconfont">&#xe786;</i>
                                    <span class="menu-text">首页</span>
                                </router-link>
                            </li>
                            <li class="tab">
                                <router-link to='/' class="tab-item">
                                    <i class="icon-menu iconfont">&#xe666;</i>
                                    <span class="menu-text">下载App</span>     
                                </router-link>
                            </li>
                        </ul>
                        <header-search></header-search>
                    </div>
                </div>
                
            </div>
        </nav>
    </div>
</template>

<script>
import HeaderSearch from './components/Search'
export default {
  name: 'Header',
  components: {
      HeaderSearch
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
@import '~styles/mixins.styl'
.nav-wrapper
    position fixed
    left 0
    right 0
    top 0
    height 56px
    min-height 50px
    background-color #fff
    border 1px solid #f0f0f0
    margin-bottom 20px
    .width-limit
        min-width 768px
        max-width 1440px
        margin 0 auto
        .logo
            float left
            height 56px
            img 
                height 100%
        .btn-right
            float right
            width 100px
            height 40px
            line-height 24px
            margin 8px 12px 0
            border-radius 20px
            color #fff
            background-color #ea6f5a
            btn()
            .icon-write
                margin-right 3px
                font-size 19px
                vertical-align middle
        .sign-up
            float right
            width 80px
            height 38px
            line-height 24px
            margin 9px 5px 0 15px
            border 1px solid rgba(236, 97, 73, .7)
            border-radius 20px
            color $orangeColor
            btn()
        .sign-in
            float right
            margin 16px 6px 0 10px
            color #969696
            btn()
        .diamond-wrapper
            float right
            height 55px
            padding 15px 0px
            margin 0 12px
            .diamond
                width 100%
                height 100%
                .img-diamond
                    height 25px
        .style-mode
            float right
            .style-mode-btn
                float right
                line-height 20px
                padding 17px 10px
                font-size 24px
                color #969696
                .icon-mode
                    font-size 22px
        .menu-container
            width 992px
            margin-right auto
            margin-left auto
            padding-left 15px
            padding-right 15px
            box-sizing border-box
            height $navHeight
            .nav-bar
                .navbar-nav
                    float left
                    margin 0
                    .tab
                        float left
                        .tab-item
                            padding 20px
                            display block
                            color #333
                            &.active
                                color $orangeColor
                            .menu-text
                                font-size 17px
                            .icon-menu
                                float left
                                font-size 22px
                                margin-right 5px
                                line-height 17px
                                



</style>