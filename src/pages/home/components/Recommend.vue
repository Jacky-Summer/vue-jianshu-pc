<template>
    <div class="board">
        <a 
            :href="item.img_href" 
            target="_blank" 
            v-for="item in list" 
            :key="item.id"
        >
            <img class="recommend-img" :src="item.img_url">
        </a>
    </div>  
</template>

<script>
export default {
    name: 'Recommend',
    props: {
        list: Array
    }
}
</script>

<style lang="stylus" scoped>
.board
    margin-top -4px
    padding-bottom 4px
    min-height 228px
    .recommend-img
        width 100%
        min-height 50px
        margin-bottom 6px
        border-radius 4px

</style>