<!-- PUG (HTML) -->
<template lang="pug">
.horizontal
    .horizontal-items
        span.name-type {{ name }}
        button.view-more XEM THÊM >
    hr
    .type-bar(v-if="typebar")
        button(
            v-for='button in buttons' 
            :key='button.id' 
            :class="{'checked-bt': selectedButton === button.id }" 
            @click='selectButton(button.id)' :style='button.style')
            | {{ button.label }}

    .items-container-horizontal
        .item-horizontal(v-for="(item, index) in items", :key="index")
            img(:src="item.image", :alt="item.title")
            span.title-story {{ item.title }}
  
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
                },
                {
                    title: "Pokemon",
                    image: img_sample,
                },
                {
                    title: "Naruto",
                    image: img_sample,
                },
                {
                    title: "Quỷ Tam Quốc",
                    image: img_sample,
                },
            ],
            selectedButton: 1,
            buttons: [
                { id: 1, label: 'Convert', style: { borderRadius: '4px 0 0 4px' } },
                { id: 2, label: 'Dịch', style: { borderRadius: 'none' } },
                { id: 3, label: 'Ngôn tình', style: { borderRadius: '0 4px 4px 0' } },
            ],
        };
    },
    methods: {
        selectButton(id) {
        this.selectedButton = id; 
        },
    },
};
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.horizontal
  padding 5% 1%
.horizontal-items
  display: flex
  justify-content: space-between
  align-items: center
  margin-bottom: 2%
.name-type
  border-left 5px solid #ef414b
  font-size: 14px
  padding-left: 2%

.items-container-horizontal
  display flex
  overflow-x auto

.item-horizontal
  width 100%
  img
    width: 90%
    height: auto
  .title-story
    font-size: 14px

.view-more
  border none
  cursor pointer
  background-color: white
  color black
  font-weight bolder
  font-size: 14px
.type-bar
    display: flex
    justify-content: center
    margin: 2% 0
    button
        width 32%
        background-color: white
        color #ef414b
        padding 1% 5%
        border 1px #ef414b solid
        border-radius: 0
    .checked-bt
        background-color: #ef414b
        color: white

</style>
