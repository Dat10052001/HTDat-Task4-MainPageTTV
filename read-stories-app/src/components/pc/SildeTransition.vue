<!-- PUG (HTML) -->
<template lang="pug">
.header-container
    .type-container-pc
        button.item-type-pc(v-for='(type, index) in typeStories' :key='index')
            i.icon-type-pc(:class='type.icon' aria-hidden="true")
            .text-type-pc
                span {{type.name}} 
                span {{type.number}}
    .image-slider-pc
        .slider-pc
            .slides-pc(:style='{ transform: `translateX(-${currentIndex * 100}%)` }')
                .slide-pc(v-for='(image, index) in images' :key='index')
                    img(:src='image.src' :alt='image.alt')
        .radio-group-pc
            label(v-for='(image, index) in images' :key='index')
                input(type='radio' name='imageSelector' :value='index' v-model='currentIndex')
                | {{image.label}}
        .top-users
            .tag-user(style='background-color: #bf2c24;')
                .tag No.1 Converter
                img(src="@/assets/user1.png") 
                span Lãnh Phong
            .tag-user(style='background-color: #327c86;')
                .tag No.1 Đại gia
                img(src="@/assets/user2.png") 
                span Yappa
            .tag-user(style='background-color: #a3af1e;')
                .tag No.1 Tiêu phí
                img(src="@/assets/user3.png") 
                span MRP
    .news-container
      h2 Tin tức
      ul
        li(v-for='(news, index) in newsList' :key='index')
          | {{ news.title }}

</template>

<!-- JAVASCRIPT  -->
<script>
import slide1 from "@/assets/slide1.jpg"
import slide3 from "@/assets/slide3.jpg"
import slide7 from "@/assets/slide7.jpg"
import slide8 from "@/assets/slide8.jpg"
import slide9 from "@/assets/slide9.jpg"

export default {
    data() {
        return {
            currentIndex: 0,
            images: [
                { src: slide1, alt: 'Ảnh 1', label: 'TTV Translate' },
                { src: slide3, alt: 'Ảnh 2', label: 'Lâm Uyên Hành' },
                { src: slide7, alt: 'Ảnh 3', label: 'Vạn Cổ Tối Cường' },
                { src: slide8, alt: 'Ảnh 4', label: 'Quỷ Bí Chi Chủ' },
                { src: slide9, alt: 'Ảnh 5', label: 'Phàm Nhân Tu Tiên' },
            ],
            typeStories: [
                { name: "Tiên Hiệp ", icon: "fa fa-dragon", number: 2022 },
                { name: "HuyềnHuyễn ", icon: "fa fa-magic", number: 493 },
                { name: " Đô Thị ", icon: "fa fa-building", number: 231 },
                { name: "KhoaHuyền ", icon: "fa fa-book", number: 1187 },
                { name: "Kỳ Huyền ", icon: "fa fa-star", number: 698 },
                { name: "Võ Hiệp ", icon: "fa fa-fist-raised", number: 474 },
                { name: "Lịch Sử ", icon: "fa fa-history", number: 1382 },
                { name: "Đồng Nhân ", icon: "fa fa-users", number: 679 },
                { name: "Quân Sự ", icon: "fa fa-shield-alt", number: 87 },
                { name: "Du Hí ", icon: "fa fa-plane", number: 1043 },
                { name: "Cảnh Kỳ ", icon: "fa fa-eye", number: 182 },
                { name: "Linh Dị ", icon: "fa fa-ghost", number: 359 },
                { name: "Ngôn Tình ", icon: "fa fa-heart", number: 1000 },
                { name: "Tất cả ", icon: "fa fa-list", number: 5000 }
            ],
            newsList: [
                { title: 'Đăng ký convert' },
                { title: 'Bảng lương convert' },
                { title: 'Kiếm tiền với Tầng Thư Viện' },
                { title: 'Các đơn vị tiền tệ' },
                { title: 'Các bước trở thành một Converter' },
                { title: 'TTV Translate - Ứng dụng convert truyện trên mobile' },
                { title: 'Tầng Thư Viện hỗ trợ chi phí cho converter' },
            ],
        };
    },
    mounted() {
        this.startAutoSlide();
    },
    methods: {
        startAutoSlide() {
            setInterval(() => {
                this.currentIndex = (this.currentIndex + 1) % this.images.length;
            }, 5000);
        },
    },
};
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.header-container
    display: flex
    width 65%
.type-container-pc
    width 24%
    height: 400px
    flex-direction: column
    flex wrap
    margin-left: 0.7%
.news-container
    width 16%
    height: auto
    margin: 1%
    background-color #f8f8f8
    border 1px solid white
    h2
        font-weight bold
        text-align: center
    ul
        list-style-type none
        padding 0
        margin 0
    li
        line-height 1.5
        padding 2%
        padding-left: 5%
        font-size: 14px
        border-bottom 1px solid #e0e0e0
        &:last-child
            border-bottom none
        &:hover
            background-color #f0f0f0
            cursor pointer 
            color red
.item-type-pc
    width 48.7%
    height: 62px
    background-color: #f6f7f2
    color black
    padding 5%
    border-radius: 0
    border: 0.01px solid white
    &:hover
        color red
.text-type-pc
    padding 2%
.icon-type-pc
    font-size: 18px
    padding 2%
    margin-bottom: 2%
.image-slider-pc
    display flex
    flex-direction column
    align-items center
    background-color white
    width 60%
    padding 1%

.slider-pc
    position relative
    width 100%
    height 280px
    overflow hidden

.slides-pc
    display flex
    transition transform 1s ease
    width 100%

.slide-pc
    min-width 100%

    img
        width 100%
        height 280px
        object-fit cover

.radio-group-pc
    width 100%
    display flex
    z-index 1
    input
        display: none
    label
        background-color: black
        color white
        width 20%
        font-size: 14px
        padding 1%
        cursor pointer
        display: flex
        justify-content: center
        align-items: center
        transition: background-color 0.3s
        filter: opacity(50%)
        margin-top: -5%
        border-right: 1px solid white
        &:hover
            background-color: rgba(0, 0, 0, 0.1)
            color grey

.top-users
    display flex
    width 100%

.tag 
    display flex
    color: white
    font-size: 14px
    align-self: flex-end
    font-weight: bolder
    padding 2%
    margin-bottom: 2%

.tag-user
    display flex
    flex-direction column
    align-items center
    width 33%
    padding 2%
    background-color: gray
    img
        width 30%
        height: 60%
        border-radius 50%
        object-fit cover
    span
        text-align center
        color white
        margin-top: 2%
            
</style>