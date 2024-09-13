<!-- PUG (HTML) -->
<template lang="pug">
.horizontal
    .horizontal-items
        span.name-type {{ name }}
        button.view-more XEM THÊM >
    hr
    .items-container-vertical
        .item-vertical(v-for='(item, index) in items' :key='index')
            img(:src='item.image' :alt='item.title')
            .info-story
                span.title-story-2 {{ item.title }}
                span.genre Thể loại: {{ item.genre }}
                span.author Tác giả: {{ item.author }}
                span.views Lượt xem: {{ item.views }}
                span.status Tình trạng: {{ item.status }}
                span.chapter Số chương: {{ item.chapter }}
</template>

<!-- JAVASCRIPT -->
<script>
import img_sample from "@/assets/sample_story.jpg"

export default {
    props: {
        name: { type: String, required: true },
        typebar: { type: Number, default: 0 },
    },
    data() {
        return {
            items: [
                {
                    title: "Kiếm Lai",
                    image: img_sample,
                    genre: "Tiên hiệp",
                    author: "Quan Hư",
                    views: 207067,
                    status: "Chưa hoàn thành",
                    chapter: 852
                },
                {
                    title: "Kiếm Lai",
                    image: img_sample,
                    genre: "Tiên hiệp",
                    author: "Quan Hư",
                    views: 207067,
                    status: "Chưa hoàn thành",
                    chapter: 852
                },
                {
                    title: "Kiếm Lai",
                    image: img_sample,
                    genre: "Tiên hiệp",
                    author: "Quan Hư",
                    views: 207067,
                    status: "Chưa hoàn thành",
                    chapter: 852
                },
                {
                    title: "Kiếm Lai",
                    image: img_sample,
                    genre: "Tiên hiệp",
                    author: "Quan Hư",
                    views: 207067,
                    status: "Chưa hoàn thành",
                    chapter: 852
                },
                {
                    title: "Kiếm Lai",
                    image: img_sample,
                    genre: "Tiên hiệp",
                    author: "Quan Hư",
                    views: 207067,
                    status: "Chưa hoàn thành",
                    chapter: 852
                },
            ],
        };
    },

}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.items-container-vertical
  display: flex
  flex-direction: column
  width 100%
.item-vertical
  width: 100%
  display: flex
  padding: 2% 0
  height: auto
  img
    width: 20%
    height: auto
    align-self: flex-start
  span
    display: block
    padding-left: 10%
    padding-bottom: 3%
    font-size: 14px
    width 100%
.title-story-2
  font-weight: bolder
</style>