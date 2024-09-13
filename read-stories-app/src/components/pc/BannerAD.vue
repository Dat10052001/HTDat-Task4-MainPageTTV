<!-- PUG (HTML) -->
<template lang="pug">
.bannerAD-pc
    img(v-if="typeAD==1" src="@/assets/banner-ad.jpg")
    img(v-else-if="typeAD==2" src="@/assets/banner-ad-2.png")
</template>

<!-- JAVASCRIPT -->
<script>

export default {
    props: {
        typeAD: { type: Number, default: 1 },
    },
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.bannerAD-pc
    text-align: center
    margin: 1% auto
    width 65%
    overflow hidden
    cursor pointer
    img
        height: auto
</style>