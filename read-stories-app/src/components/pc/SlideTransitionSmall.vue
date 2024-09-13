<!-- PUG (HTML) -->
<template lang="pug">
.body-slider-small
    .image-slider-small
        .slider-small
            .slides-small(:style='{ transform: `translateX(-${currentIndex * 100}%)` }')
                .slide-small(v-for='(image, index) in images' :key='index')
                    img(:src='image.src' :alt='image.alt')
        .radio-group-small
            label(v-for='(image, index) in images' :key='index')
                input(type='radio' name='imageSelector' :value='index' v-model='currentIndex')
    .featured
        span.title {{ images[currentIndex].title }}
        span.detail {{ images[currentIndex].detail }}
        button.hover-pink Đọc truyện
</template>

<!-- JAVASCRIPT  -->
<script>
import slide_sample from "@/assets/sample_story.jpg"

export default {
    data() {
        return {
            currentIndex: 0,
            images: [
                { src: slide_sample, title: 'Kiếm Lai', detail: 'Thế giới rộng lớn không thiếu cái lạ' },
                { src: slide_sample, title: 'Quỳ Tam Quốc', detail: 'Nhân loại tiến vào tinh tế thời đại' },
                { src: slide_sample, title: 'Tiên Nhân Biến Mất', detail: 'Dưới đất có người, thế gian không có tiên' },
                { src: slide_sample, title: 'Tâm Linh Chúa Tể', detail: 'Hỗn Độn chân giới bị Ma Uyên chân giới mở '},
                { src: slide_sample, title: 'Trùng Sinh 2011', detail: 'Hơn mười năm trước, tỉnh nội hạng nhất đại học' },
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
.body-slider-small
    width: 100%
    padding 1% 0
    display: flex
    border-bottom 1px solid #e0e0e0

.image-slider-small
    display flex
    flex-direction column
    align-items center
    width 40%
    padding 2% 0
.hover-pink
    &:hover
        background-color: #ed4259
        cursor pointer

.slider-small
    position relative
    width 40%
    height 170px
    overflow: hidden

.slides-small
    display flex
    transition transform 1s ease
    width 100%

.slide-small
    min-width 100%
    text-align: center
    img
        width: auto
        height: 120px
.radio-group-small
    display flex
    justify-content center
    z-index 1
    accent-color: red
    margin-top: -18%

.featured
    width: 60%
    padding-top: 1%
    button
        border 1px solid white
        background-color: #bf2c24
        color: white
        border-radius: 15px
        padding 2% 5% 
        margin 2%
        margin-top: 5%
    span
        display: block
        margin 2%
    .title
        font-weight: bolder
        font-size: 18px
        padding-bottom: 2%
    .detail
        font-size: 14px
        color gray
</style>