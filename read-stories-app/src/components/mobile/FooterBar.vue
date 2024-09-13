<!-- PUG (HTML) -->
<template lang="pug">
footer.footer-bar
  .footer-links
    span.footer-link IOS
    span.footer-link Android
    span.footer-link PC
    span.footer-link Nội quy
  .footer-copy
    p copyright &copy; 2017 Tầng thư viện mobile
.spacing
</template>

<!-- JAVASCRIPT -->
<script>
export default {
    name: 'FooterBar',
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.footer-bar
  display flex
  flex-direction column
  align-items center
  padding 2% 0
  background-color #f8f9fa
  border-top 1px solid #e9ecef

.footer-links
  display flex
  justify-content center
  width: 100%

.footer-link
  width: 25%
  font-weight bold
  cursor pointer
  text-align: center
  padding 2% 0

.footer-copy
  font-size 14px
  color #6c757d
.spacing
  height: 50px
</style>