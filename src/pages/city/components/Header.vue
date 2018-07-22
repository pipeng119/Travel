<template>
    <div class="header">
        城市选择
        <router-link to="/">
            <div class="iconfont header-back">&#xe624;</div>
        </router-link>
    </div>
</template>
<script>
export default {
    name: 'cityHeader',
    data(){
        return {

        }
    }
}
</script>
<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .header 
        overflow hidden
        position relative
        height $headerHeight
        line-height $headerHeight
        text-align center
        font-size .32rem
        color #fff
        background $bgColor
        .header-back
            position absolute
            top 0
            left 0
            width .64rem
            text-align center
            font-size .4rem
            color #fff
</style>
