<!-- PUG (HTML) -->
<template lang="pug">
.image-slider
    .slider
        .slides(:style='{ transform: `translateX(-${currentIndex * 100}%)` }')
            .slide(v-for='(image, index) in images' :key='index')
                img(:src='image.src' :alt='image.alt')
    .radio-group
        label(v-for='(image, index) in images' :key='index')
            input(type='radio' name='imageSelector' :value='index' v-model='currentIndex')
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
                { src: slide1, alt: 'Ảnh 1', label: 'Ảnh 1' },
                { src: slide3, alt: 'Ảnh 2', label: 'Ảnh 2' },
                { src: slide7, alt: 'Ảnh 3', label: 'Ảnh 3' },
                { src: slide8, alt: 'Ảnh 4', label: 'Ảnh 4' },
                { src: slide9, alt: 'Ảnh 5', label: 'Ảnh 5' },
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
    .image-slider
        display flex
        flex-direction column
        align-items center
        background-color #f6f7f9
        width 100%
        padding 2% 0

    .slider
        position relative
        width 100%
        height 170px
        overflow hidden

    .slides
        display flex
        transition transform 1s ease
        width 100%

    .slide
        min-width 100%

        img
            width 100%
            height 170px
            object-fit cover

    .radio-group
        display flex
        justify-content center
        margin-top -4%
        z-index 1
        accent-color: red
</style>