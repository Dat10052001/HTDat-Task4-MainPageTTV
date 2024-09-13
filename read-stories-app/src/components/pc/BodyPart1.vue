<!-- PUG (HTML) -->
<template lang="pug">
  .container-body1
    .left-panel
      h2 Truyện mới xem
      hr
      ul
        li(v-for='(truyen, index) in truyenMoiXem' :key='index')
          | {{ truyen.title }}
          span.color-gray {{ truyen.chuong }}
    .center-panel
      h2 Biên tập viên đề cử
      hr
      SlideTransitionSmallVue
      .recommended
        button.book-item(v-for='(book, index) in books' :key='index')
          span.title-book {{ book.title }}
          span {{ book.chuong }} chương
          span {{ book.detail }}
    .right-panel
      .title-list-1
        h2 Đang theo dõi
        button.view-more-2.hover-blue Tất cả >
      hr
      ul
        li(v-for='(truyen, index) in dangTheoDoi' :key='index')
          | {{ truyen.title }}
          span.color-gray {{ truyen.chuong }}

</template>

<!-- JAVASCRIPT -->
<script>
import SlideTransitionSmallVue from './SlideTransitionSmall.vue';

export default {
  components: {
    SlideTransitionSmallVue,
  },
  data() {
    return {
      truyenMoiXem: [
        { title: 'Quỳ Tam Quốc', chuong: 'Chương 1' },
        { title: 'Ai Bảo Hán Tu Tiên', chuong: 'Chương 1' },
        { title: 'Khai Cực Nữ Ma Đế', chuong: 'Chương 1' },
        { title: 'Kiếm Lai', chuong: 'Chương 1' },
        { title: 'Túc Mệnh Chi Hoàn', chuong: 'Chương 1' },
        { title: '[Dịch] Kiếm Lai - Tàng Thư Viện', chuong: 'Chương 1' },
        { title: 'Luân Hồi Lạc Viễn', chuong: 'Chương 1' },
        { title: 'Cửu Vực Phạm Tiên', chuong: 'Chương 1' },
        { title: 'Trần Vấn Trường', chuong: 'Chương 1' },
        { title: 'Các Người Tu Tiên', chuong: 'Chương 1' },
        { title: 'Mỹ Ngư Chi Hoa Binh', chuong: 'Chương 1' },
        { title: 'Cháp Ma', chuong: 'Chương 1' },
        { title: 'Tiên Mộc Kỳ Duyên', chuong: 'Chương 1' },
        { title: 'Ô Long Sơn Tu Tà', chuong: 'Chương 1' },
      ],
      books: [
        { title: 'Trần Vấn Trường Sinh', chuong: 853, detail: "Tu giới Cửu Châu, Đạo Đình nhất thống, thế gia áp bách...", },
        { title: 'Mỹ Ngư Chi Hoa Bình Ảnh Đế', chuong: 1015, detail: "Tại ngày đó, sương mù dày đặc phong tỏa hết thảy. Tại ngày đó,...", },
        { title: 'Luân Hồi Lạc Viễn', chuong: 4242, detail: "Thế giới này thời cổ có nhiều kẻ nứt liên thông với quỷ dị thế...", },
        { title: 'Cửu Vực Phàm Tiên', chuong: 230, detail: "Vâng, ta chính là bình hoa!", },
        { title: 'Có Chương Ô Thác Bàng', chuong: 230, detail: "Cơ thể giả kim loại cải tiến, bạn gái AI, trong đầu mạng...", },
        { title: 'Thâm Hải Dư Tẫn (Tro Tàn)', chuong: 230, detail: "Tô Hiểu ký kết Luân Hồi khế ước, tiến vào từng thế giới...", },
      ],
      dangTheoDoi: [
        { title: 'Trần Vấn Trường Sinh', chuong: 853 },
        { title: 'Thám Hải Dư Tấn (Tro Tàn)', chuong: 862 },
        { title: 'Tuyệt Cảnh Hắc Dạ', chuong: 162 },
        { title: 'Mỹ Ngư Chi Hoa Bình', chuong: 1015 },
        { title: 'Luân Hồi Lạc Viễn', chuong: 4242 },
        { title: 'Có Chương Ô Thác Bàng', chuong: 230 },
        { title: 'Tinh Không Chức Nghiệp', chuong: 247 },
        { title: 'Có Chương Ô Thác Bàng', chuong: 449 },
        { title: 'Ngự Thú: Ta Có Thể Vô Hạn Tiến Hóa', chuong: 190 },
        { title: 'Vô Thượng Thiên Tôn', chuong: 288 },
        { title: 'Tiên Nhân Biến Mất', chuong: 2178 },
        { title: 'Ai Bảo Hắn Tu Tiên!', chuong: 143 },
        { title: 'Cửu Vực Phàm Tiên', chuong: 346 },
        { title: 'Ai Đem Thi Thể Của Ta Ẩn Nấp Rồi!', chuong: 330 },
      ],
    };
  },
};
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.container-body1
  width: 65%
  display flex
  margin 0 auto
.title-list-1
  display: flex
  justify-content: space-between
  align-items: center
  margin-bottom: -3%
.left-panel, .right-panel
  padding 2% 0
  width 22%
  li
    display: flex
    justify-content: space-between
    font-size: 13px
    border-bottom 1px solid #e0e0e0
    padding 2.2% 0
    &:hover
      color red
      cursor pointer
.color-gray
  color gray
.hover-blue
  &:hover
    color blue
.center-panel
  padding 2%
  width 56%

h2
  font-size 18px
  font-weight: 100
ul
  list-style-type none
  padding 0
.recommended
  display flex
  flex-wrap wrap
  padding-top: 1%

.book-item
  border: none
  border-bottom 1px solid #e0e0e0
  width 33%
  padding-right: 3%
  background-color: white
  text-align: start
  .title-book
    color #333
    padding 1% 0
    font-size: 17px
    &:hover 
      cursor pointer
      color red
  span
    display block
    font-size 12px
    color #777
    margin-bottom 5px
    &:nth-child(2)
      color red
      font-weight bold

</style>