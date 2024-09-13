<!-- PUG (HTML) -->
<template lang="pug">
.body-part-3

    ListHorizontalVue(src=2, name="Top Conventers", total=0, nameNumber="chương")

    .main-body-3
        .story-detail
            span.name-type-2 Mới cập nhật
            button.view-more-2.hover-blue Xem Thêm >
        hr
        .five-details(v-for="(item, index) in books" :key="index")
            span.type {{ item.type }}
            span.title {{ item.title }}
            span.chapter Chương {{ item.chapter }}
            span.author {{ item.author }}
            span.time {{ item.time }}

    ListHorizontalVue(src=3, name="Top Đại gia", total=0, nameNumber="thạch")

</template>

<!-- JAVASCRIPT -->
<script>
import ListHorizontalVue from './ListHorizontal.vue'

export default {
    components: {
        ListHorizontalVue,
    },
    data() {
        return{
            books: [
                { title: "Nhĩ Giả Linh Chủ Hữu Vấn Đề Ba", type: "Du Hí", chapter: 800, author: "Thái Bạch Thủy Quan", time: "14:06 13/09" },
                { title: "Tinh Không Chức Nghiệp Giả", type: "Khoa Huyền", chapter: 249, author: "Văn Sao Cộng", time: "13:53 13/09" },
                { title: "Quý Dị Giáng Lâm? May Mà Ta Là Thật", type: "Linh Dị", chapter: 805, author: "Thái Nguyệt Bất Cật Qua", time: "13:11 13/09" },
                { title: "Tuyệt Thế Ma Thế, Ta Chỉ Muốn Sống Tạm", type: "Huyền Huyễn", chapter: 558, author: "Diệp Phi Diệp", time: "13:08 13/09" },
                { title: "Ôn Noãn Đích Long", type: "Kỳ Huyễn", chapter: 715, author: "Bạch Vũ Hạm", time: "13:07 13/09" },
                { title: "Hắn Có Khái Niệm Cấp Năng Lực", type: "Linh Dị", chapter: 508, author: "Thái Nguyệt Bất Cật Qua", time: "12:57 13/09" },
                { title: "Hắc Thạch Mật Mã", type: "Đỗ Thị", chapter: 2734, author: "Tam Cược Giá", time: "12:49 13/09" },
                { title: "Trọng Hồi 1982 Tiểu Ngư Thôn", type: "Linh Dị", chapter: 1228, author: "Mễ Phan Đích Mễ", time: "12:31 13/09" },
                { title: "Tình Thâm Tới Muộn Thua Cỏ Rác", type: "Đỗ Thị", chapter: 431, author: "Lap Lạp Tiểu Nam Qua", time: "12:20 13/09" },
                { title: "Quỷ Tam Quốc", type: "Lịch Sử", chapter: 2505, author: "Mã Nguyệt Hầu Niên", time: "12:03 13/09" },
                { title: "Ngã Đích Hoàn Mỹ Mạt Thế Nhân Sinh", type: "Khoa Huyền", chapter: 295, author: "Trường Kinh Quy Hải", time: "11:53 13/09" },
                { title: "Thiên Tài Câu Lạc Bộ", type: "Khoa Huyền", chapter: 955, author: "Thành Thành Dữ Thiền", time: "11:49 13/09" },
                { title: "Túc Mệnh Chi Hoàn", type: "Huyền Huyễn", chapter: 96, author: "Ái Tiềm Thủy đích Ô Tạc", time: "11:43 13/09" },
                { title: "Trùng Sinh 2011", type: "Đỗ Thị", chapter: 243, author: "Bất Tựy Xuân Thư", time: "11:41 13/09" },
                { title: "Thiên Quan Tứ Tà", type: "Linh Dị", chapter: 363, author: "Huyền Mộng Liệp Nhân", time: "11:41 13/09" }
            ],
        }
    }
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.body-part-3
    width 65%
    display: flex
    margin: 0 auto
.main-body-3
    width 80%
    padding 1%
.story-detail
    display: flex
    justify-content: space-between
.five-details
  display flex
  justify-content space-between
  border-bottom: 1px solid #e0e0e0
  span
    flex 1
    padding 0.9% 1% 
    &:hover
        color red
  .type
    flex 1
    font-size: 11px
    color gray
  .title
    flex 4
    font-size: 14px
  .chapter
    flex 1
    font-size: 11px
  .author
    flex 2
    font-size: 12px
    color gray
  .time
    flex 1
    font-size: 12px
</style>