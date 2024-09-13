<!-- PUG (HTML) -->
<template lang="pug">
footer.footer-bar-pc
  .footer-content
    .footer-logo
      img(src='@/assets/logo-web-gray.png' alt='Logo')
    .footer-text
      span &copy; 2007 Tàng Thư Viện - Chính sách
      br
      span Tàng Thư Viện là sân chơi mở và free cho cộng đồng fan kiếm hiệp, tiên hiệp, ngôn tình. Chúc các bạn có những giây phút thư giãn thoải mái sau giờ làm việc và học tập căng thẳng.

</template>

<!-- JAVASCRIPT -->
<script>
export default {
  
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.footer-bar-pc
    width 100%
    background-color: #f8f8f8
    display: flex
    justify-content: center
.footer-content
    display flex
    padding 1% 0
    background-color #f8f8f8
    border-top 1px solid #e9ecef
    width 65%
    align-items: center;
.footer-logo
    width 25%
    margin-right: 6%
    img
        width: 100%
.footer-text
    font-size: 15px
    color gray
    span 
        margin-bottom: 5%
</style>