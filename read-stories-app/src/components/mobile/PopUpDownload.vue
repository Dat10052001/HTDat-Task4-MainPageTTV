<!-- PUG (HTML) -->
<template lang="pug">
.popup(v-if='visible')
  .popup-content
    img.popup-logo(src='@/assets/logo-img.png' alt='Logo')
    span.popup-message Tải app TTV để sử dụng đầy đủ chức năng
</template>

<!-- JAVASCRIPT -->
<script>
export default {
    name: 'PopupDownload',
    data() {
        return {
            visible: true, 
        };
  },
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.popup
  position fixed
  bottom 20px
  left 50%
  transform translateX(-50%)
  background-color #349b9a
  border-radius 20px
  padding 1% 5%
  box-shadow 0 2px 10px rgba(0, 0, 0, 0.2)
  z-index 1000
  width 80%

.popup-content
  display flex
  align-items center
  justify-content: center

.popup-logo
  width 30px
  height auto
  margin-right 2%

.popup-message
  color white
  font-size 14px
</style>