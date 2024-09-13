<!-- PUG (HTML) -->
<template lang="pug">
.list-container
    .title-list
        span.name-type-2 {{ name }}
        button.view-more-2.hover-blue(v-if="total==1") Tất cả >
    hr
    .no-1
        .text-story
            span.rank NO.1
            span.title-part-2 {{ currentData[0].title }}
            span.chuong {{ currentData[0].chuong }} {{ nameNumber }}
            span.author(v-if="total==1") Tiên hiệp . Quan hư
        img(v-if="src==1" src='@/assets/sample_story.jpg')
        img(v-if="src==2" src='@/assets/user1.png')
        img(v-if="src==3" src='@/assets/user2.png')
    ul
        li(v-for='(item, index) in currentData' :key='index')
            .from-2(v-if='index > 0')
                span {{ index+1 }}
                a
                    span {{ item.title }}
                span.color-gray {{ item.chuong }}
</template>

<!-- JAVASCRIPT -->
<script>
export default {
    props: {
        name: { type: String, required: true },
        total: { type: Number, default: 1 },
        nameNumber: { type: String, required: true },
        src: { type: Number, default: 1},
    },
    data() {
        return{
            stories: [
                { title: 'Trần Vấn Trường Sinh', chuong: 853 },
                { title: 'Thám Hải Dư Tấn (Tro Tàn)', chuong: 862 },
                { title: 'Tuyệt Cảnh Hắc Dạ', chuong: 162 },
                { title: 'Mỹ Ngư Chi Hoa Bình', chuong: 1015 },
                { title: 'Luân Hồi Lạc Viễn', chuong: 4242 },
                { title: 'Có Chương Ô Thác Bàng', chuong: 230 },
                { title: 'Tinh Không Chức Nghiệp', chuong: 247 },
                { title: 'Có Chương Ô Thác Bàng', chuong: 449 },
                { title: 'Ta Có Thể Vô Hạn Tiến Hóa', chuong: 190 },
                { title: 'Vô Thượng Thiên Tôn', chuong: 288 },
            ],
            users2: [
                { title: 'Yappa ', chuong: 211388 },
                { title: 'luoihoc', chuong: 124530 },
                { title: 'nvccanh', chuong: 39025 },
                { title: 'quangtri1255', chuong: 35289 },
                { title: 'qsr1009', chuong: 29777 },
                { title: 'Phong Nhân Nhân', chuong: 28886 },
                { title: 'Oikawa77', chuong: 24771 },
                { title: 'nguoinhanbi2010', chuong: 21664 },
                { title: 'mai2001', chuong: 21000 },
                { title: 'fishscreen', chuong: 20387 },
            ],
            users1: [
                { title: 'Lãnh Phong', chuong: 5258 },
                { title: 'vohansat', chuong: 1517 },
                { title: 'RyuYamada', chuong: 1412 },
                { title: 'nguoinhanbi2010', chuong: 1116 },
                { title: 'hanals', chuong: 957 },
                { title: 'why03you', chuong: 507 },
                { title: 'viettieuv', chuong: 481 },
                { title: 'trankhac', chuong: 243 },
                { title: 'Siêu Cấp Thuần Khiết', chuong: 240 },
                { title: 'Illyn142', chuong: 172 },
            ]
        }
    },
    computed: {
        currentData() {
            if (this.src == 2) {
                return this.users1;
            } else if (this.src == 3) {
                return this.users2;
            } else {
                return this.stories;
            }
        },
    }
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.list-container
  padding 1%
  width 25%
  .from-2
    display: flex
    justify-content: space-between  
    font-size: 13px
    border-bottom 1px solid #e0e0e0
    padding 5% 0
    cursor pointer
    &:hover
        color red
        
.title-list
  display: flex
  justify-content: space-between
  align-items: center
  margin-bottom: 2%
.name-type-2
  font-size: 18px

.view-more-2
  border none
  cursor pointer
  background-color: white
  color gray
  font-size: 14px
.no-1
    display: flex
    height: auto
    img
        width: 30%
        justify-self end
    &:hover
        cursor pointer
.text-story
    width: 70%
    span 
        display: block
        padding 2%
.rank
    background-color: red
    color white
    width fit-content
.title-part-2
    font-weight: bolder
.chuong
    font-style: italic
    color red
</style>