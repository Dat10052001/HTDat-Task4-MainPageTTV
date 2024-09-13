<!-- PUG (HTML) -->
<template lang="pug">
.header
    .header-mobile
        .left-header
            span.name-web Tàng thư viện
            button.bt-forum Diễn đàn
        .right-header
            button.bt-dl-app 
                i.fa.fa-download(aria-hidden="true") 
                span App
            button.bt-sign
                i.fa-regular.fa-user(aria-hidden="true")
    SlideTransition
    .search-bar
        input.search-input(type="text" placeholder=" Tìm kiếm")
        span
            i.fa.fa-search(aria-hidden="true")
.nav-header
    button.nav-item(
        v-for="(item, index) in navItems"
        :key="index"
    )
        i(:class="item.icon" :style="{ color: item.color }")
        span {{item.label}}
</template>

<!-- JAVASCRIPT -->
<script>
import SlideTransition from './SlideTransition.vue'

export default {
    data(){
        return{
            navItems: [
                { label: 'Thể loại', icon: 'fa fa-th', color: '#00bcd4' },
                { label: 'Xếp hạng', icon: 'fa fa-bar-chart', color: '#f44336' },
                { label: 'Bộ lọc', icon: 'fa fa-filter', color: '#ff9800' },
                { label: 'Top User', icon: 'fa fa-crown', color: '#9c27b0' },
                { label: 'Review', icon: 'fa fa-folder', color: '#ffeb3b' },
            ],
        }
    },
    components: {
        SlideTransition,
    }
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.header
    width 96%
    background-color: #f6f7f9
    padding 2%
.header-mobile
        display flex
        width 100%

    .left-header
        display flex
        justify-content flex-start
        width 50%
        .name-web
            font-weight bolder
            padding-top: 1%
        .bt-forum
            padding 2% 5%
            border 1px solid red
            color red
            background-color white
            border-radius 4px
            margin-left: 5%

    .right-header
        display flex
        justify-content flex-end
        width 50%
        .bt-dl-app
            display: flex
            border: none
            background-color: #349b9a
            color white
            border-radius: 2px
            align-items: center
            justify-content: center
            width 27%
            span
                margin-left: 10%
        .bt-sign
            border none
            margin-left: 2%
            background-color: #f6f7f9
            .fa-user
                color red

    .search-bar
        position relative
        padding 2% 0
        margin-top: 2%
        .fa-search
            position: absolute;
            left: 35%
            top: 50% 
            transform: translateY(-50%) 
            pointer-events: none
    .search-input
        width 100%
        padding 2% 0
        text-align: center
        background-color: white
        border: none
        &:focus
            border none
            outline none
            box-shadow: none

    .nav-header
        display flex
        justify-content space-around
        padding 2% 0
        background-color: white

    .nav-item
        display flex
        flex-direction column
        align-items center
        text-decoration none
        border: none
        background-color: white
        i
            font-size 24px
            margin-bottom 10%
</style>