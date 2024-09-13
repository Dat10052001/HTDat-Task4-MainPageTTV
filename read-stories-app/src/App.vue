<!-- PUG (HTML) -->
<template lang="pug">
.body

  .mobile
    HeaderMobile

    BannerADMobile

    HorizontalItems(name="TRUYỆN MỚI CẬP NHẬT" typebar="true")

    HorizontalItems(name="TRUYỆN XEM NHIỀU")

    VerticalItems(name="TRUYỆN ĐỀ CỬ THÁNG")

    BannerADMobile

    VerticalItems(name="TRUYỆN ĐÃ HOÀN THÀNH")

    FooterMobile

    PopupDownload
  
  .pc
    HeaderPC

    BodyPart1

    BannerADPC

    BodyPart2

    BannerADPC(typeAD=2)

    ListSquare(name="Truyện mới")

    BodyPart3

    BannerADPC

    ListSquare(name="Truyện đã hoàn thành")

    FooterPC

</template>

<!-- JAVASCRIPT -->
<script>
import BannerADMobile from './components/mobile/BannerAD.vue'
import HorizontalItems from './components/mobile/HorizontalItems.vue'
import VerticalItems from './components/mobile/VerticalItems.vue'
import PopupDownload from './components/mobile/PopUpDownload.vue'
import HeaderMobile from './components/mobile/HeaderBar.vue'
import FooterMobile from './components/mobile/FooterBar.vue'

import BannerADPC from './components/pc/BannerAD.vue'
import HeaderPC from './components/pc/HeaderBar.vue'
import FooterPC from './components/pc/FooterBar.vue'
import BodyPart1 from './components/pc/BodyPart1.vue'
import BodyPart2 from './components/pc/BodyPart2.vue'
import BodyPart3 from './components/pc/BodyPart3.vue'
import ListSquare from './components/pc/ListSquare.vue'

export default {
  name: 'App',
  components: {
      BannerADMobile,
      HorizontalItems,
      VerticalItems,
      PopupDownload,
      HeaderMobile,
      FooterMobile,
      HeaderPC,
      BannerADPC,
      BodyPart1,
      BodyPart2,
      ListSquare,
      BodyPart3,
      FooterPC,
  },
}
</script>

<!-- STYLUS (CSS) -->
<style lang="stylus">
  .body
    font-family Arial, '-apple-system', Simsun
    @media (min-width 480px)
      .mobile
        display: block
      .pc
        display: none
    @media (min-width 1280px)
      .mobile
        display: none
      .pc
        display: block
</style>