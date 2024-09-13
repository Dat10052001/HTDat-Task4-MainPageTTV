<!-- PUG (HTML) -->
<template lang="pug">
.new-stories
    .new-title-stories
        span.name-type-2(style="font-size: 18px") {{ name }}
        button.total-new.hover-blue(v-if="total") Xem thêm >
    hr
    .container-items-stories
        .block-item-1
            img(src="@/assets/sample_story.jpg")
            h4.hover-red Đô Thị Cực Phẩm Tiên Tôn
            span.authorleft Hữu Điểm Đông Tây
            span.chuongleft 1092 chương
            span Vượt lên ngàn tỉ tinh cầu bên trên đệ nhất tiên tôn Tần Mục độ kiếp thất bại
        .block-items-right
            button.book-item-2(v-for='(story, index) in stories' :key='index')
                img(src="@/assets/sample_story.jpg")
                .info-right
                    span.title-book-2 {{ story.title }}
                    span {{ story.detail }}
                    span    
                        i.fa.fa-user-circle
                        p {{ story.author }} 
                

</template>

<!-- JAVASCRIPT -->
<script>
export default {
    props: {
        name: { type: String, required: true },
        total: { type: Boolean, default: true },
        nameNumber: { type: String, required: true },
    },
    data() {
        return{
            stories: [
                { title: 'Thám Hải Dư Tấn (Tro Tàn)', chuong: 862, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
                { title: 'Tuyệt Cảnh Hắc Dạ', chuong: 162, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
                { title: 'Mỹ Ngư Chi Hoa Bình', chuong: 1015, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
                { title: 'Luân Hồi Lạc Viễn', chuong: 4242, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
                { title: 'Có Chương Ô Thác Bàng', chuong: 230, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
                { title: 'Tinh Không Chức Nghiệp', chuong: 247, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
                { title: 'Có Chương Ô Thác Bàng', chuong: 449, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
                { title: 'Ta Có Thể Vô Hạn Tiến Hóa', chuong: 190, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
                { title: 'Vô Thượng Thiên Tôn', chuong: 288, detail: "Hơn mười năm trước, tỉnh nội hạng nhất đại học", author: "Bút Điểm Yên Hoa" },
            ],
        }
    }
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.new-stories
    width: 65%
    margin: 2% auto
.new-title-stories
    display: flex
    justify-content: space-between
.total-new
    border none
    cursor pointer
    background-color: white
    color gray
    font-size: 14px
.container-items-stories
  display flex
.hover-red
    &:hover
        color red
        cursor pointer
.block-item-1
  width 40%
  background-color #f7f5f0
  display: flex
  flex-direction: column
  align-items center
  justify-content center
  text-align: center
  span
    padding 2% 0
    font-size: 12px
.chuongleft
    font-weight: bolder
.authorleft
    color red
    font-weight: bolder
    font-style: italic
.block-items-right
  display flex
  flex-wrap wrap
  margin-left: 2%

.book-item-2
  display: flex
  padding 2%
  border: none
  border-bottom 1px solid #e0e0e0
  width 33%
  padding-right: 3%
  background-color: white
  text-align: start
  align-items: center
  
  .info-right
    flex-grow: 1
    margin-left: 5%
  img
    width 25%
    height: auto
    transition transform 0.3s ease
    &:hover
        cursor pointer
        transform scale(1.2)
  .title-book-2
    color #333
    padding 1% 0
    font-size: 15px
    &:hover
        color red
        cursor pointer
  span
    display block
    font-size 12px
    color #777
    p 
      display: inline-block
      margin-left: 2%

</style>