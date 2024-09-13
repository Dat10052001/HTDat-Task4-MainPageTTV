<!-- PUG (HTML) -->
<template lang="pug">

header.header-pc
  .container-header
      img(src='@/assets/logo-full.png' alt='Logo')
      input(type='text' placeholder='Nhập tên truyện hoặc tác giả..')
      button.search-button
          i.fa.fa-search(aria-hidden='true')
      button.acc-bt(id="show-modal" @click="showModal = true")
          i.fa.fa-address-card(aria-hidden='true')
          span Tài khoản
  .header-navbar
      button.navbar-item.item-l
          i.fa.fa-bars(aria-hidden='true')
          span Thể loại
      button.navbar-item Diễn đàn
      button.navbar-item Bảng xếp hạng
      button.navbar-item Bộ lọc
      button.navbar-item Review
      button.navbar-item Cửa hàng
      button.navbar-item.item-r
          i.fa.fa-mobile(aria-hidden='true')
          span Tải app
  SlideTransition
  FormModal(:show="showModal" @close="showModal = false")

</template>

<!-- JAVASCRIPT -->
<script>
import FormModal from './FormModal.vue'
import SlideTransition from "./SildeTransition.vue"

export default {
  components: {
    SlideTransition,
    FormModal,
  },
  data() {
    return {
      showModal: false
    }
  }
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.header-pc
  display flex
  flex-direction column
  align-items center

.container-header
  display flex
  color white
  width 64%
  padding-top: 1%
  justify-content: space-between
  img
    width auto
    height 50px
  input
    width 30%
    padding 0 1%
    height 40px
    border 1px solid #e6e6e6
    margin-left: -5%
    &:focus
      outline none
      box-shadow none

.search-button
  padding 0 0.8%
  background-color #2798a1
  color white
  cursor pointer
  height 42px
  border 1px solid #e6e6e6
  margin-left: -20%
  i
    font-size 20px
  &:hover
    background-color #ed4259
    border none
    cursor pointer
  

.acc-bt
  height 40px
  background-color white
  color black
  border 1px solid #e6e6e6
  padding 0 1.5%
  width 12%
  &:hover
    color white
    background-color #ed4259
    border none
    cursor pointer
  i
    font-size 20px
    margin-right 5%
  span
    font-style italic
    font-size 16px
.header-navbar  
  margin-top: 1%
  display: flex
  width: 100%
  background-color: #2798a1
  justify-content: center
.navbar-item
  padding 0.6% 0
  display flex
  align-items center
  background-color #2798a1
  border 2px solid #2798a1
  color white
  font-size 14px
  cursor pointer
  width 8%
  justify-content: center
  &:hover
    border-top: 2px solid red
    background-color: #077c86
.item-l
  width 14.5%
  background-color: #077c86
  justify-content: flex-start
  margin-left: 2.4%
  &:hover
    border 2px solid #2798a1
  i
    margin: 0 5%
.item-r
  width: 12%
  justify-content: center
  &:hover
    background-color #2798a1
    border 2px solid #2798a1
    color greenyellow
  i
    margin: 0 5%
</style>