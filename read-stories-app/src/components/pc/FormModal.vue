<!-- PUG (HTML) -->
<template lang="pug">
  transition(name='modal')
    .modal-mask(v-if='show')
      .modal-container
        .modal-header
          slot(name='header')
            button(:class="{ 'bt-checked': isLoginVisible, 'bt-uncheck': !isLoginVisible }"  @click="showLogin") Đăng nhập 
            button(:class="{ 'bt-checked': !isLoginVisible, 'bt-uncheck': isLoginVisible }"  @click="showRegister") Đăng ký mới
            button.modal-default-button(@click="$emit('close')") X
        .modal-body-1(v-if="isLoginVisible")
          slot(name='body')
            .input-login
              i.fa-solid.fa-user
              input(placeholder="Tài khoản" type="text")
            .input-login
              i.fa-solid.fa-lock
              input(placeholder="Mật khẩu" type="password")
            button.forgot-password Quên mật khẩu ?
            button.bt-sign-cf Đăng nhập
            button.sign-up-fb
              i.fa-brands.fa-facebook(aria-hidden='true')
              span Đăng nhập bằng Facebook
        .modal-body-2(v-if="!isLoginVisible")
          slot(name='body')
            .input-login
              i.fa-solid.fa-user
              input(placeholder="Tài khoản" type="text")
            .input-login
              i.fa-solid.fa-user
              input(placeholder="Email" type="text")
            .input-login
              i.fa-solid.fa-lock
              input(placeholder="Mật khẩu" type="password")
            .input-login
              i.fa-solid.fa-lock
              input(placeholder="Nhập lại mật khẩu" type="password")
            button.bt-sign-cf Đăng ký

</template>

<!-- JAVASCRIPT -->
<script>
export default {
  props: {
    show: Boolean
  },
  data() {
    return {
      isLoginVisible: true, 
    };
  },
  methods: {
    showLogin() {
      this.isLoginVisible = true; 
    },
    showRegister() {
      this.isLoginVisible = false; 
    },
  },
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.bt-checked
  border none
  border-bottom: 2px solid #bf2c24
  background-color: white
  width 48%
  padding-bottom: 5%
  font-size: 18px
.bt-uncheck
  border none
  border-bottom: 2px solid gray
  background-color: white
  width 48%
  padding-bottom: 5%
  font-size: 18px
  color gray
.modal-body-1
.modal-body-2
  padding 10% 0 5% 2%
.input-login
  padding 5% 1%
  i
    font-size: 24px
    margin-right: 5%
  input
    width: 80%
    padding 3% 2%
    font-size: 14px
    &:focus
      outline: none
.bt-sign-cf
  background-color: #bf2c24
  width 96%
  padding 3% 0
  color white
  font-size: 16px
  border: none
  margin-top: 5%
  &:hover
    cursor pointer
    background-color: #ed4259
.forgot-password
  float: right
  border: none
  background-color: white
  margin-right: 3%
  &:hover
    cursor pointer
.sign-up-fb
  background-color: white
  width 96%
  padding 3% 0
  color blue
  font-size: 16px
  border: none
  margin-top: 5%
  i
    margin-right: 2%
  &:hover
    cursor pointer
    background-color: #f0f5ff
.modal-mask
  position fixed
  z-index 9998
  top 0
  left 0
  width 100%
  height 100%
  background-color rgba(0, 0, 0, 0.5)
  display flex
  transition opacity 0.3s ease

.modal-container
  width 18%
  margin auto
  padding 20px 30px
  background-color #fff
  border-radius 2px
  box-shadow 0 2px 8px rgba(0, 0, 0, 0.33)
  transition all 0.3s ease

.modal-header
  h3
    margin-top 0
    color #42b983

.modal-body
  margin 20px 0

.modal-default-button
  padding 2% 4%
  float right
  background-color: #bf2c24
  color white
  border none
  margin-right: -9%
  margin-top: -6%
  &:hover
    cursor pointer

.modal-enter-from
  opacity 0

.modal-leave-to
  opacity 0

.modal-enter-from .modal-container,
.modal-leave-to .modal-container
  -webkit-transform scale(1.1)
  transform scale(1.1)
</style>