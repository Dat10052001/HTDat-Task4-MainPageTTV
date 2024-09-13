<!-- PUG (HTML) -->
<template lang="pug">
.body-part-2

    ListHorizontalVue(name="Đề cử", nameNumber="để cử")
    
    ListHorizontalVue(name="Xem nhiều", nameNumber="lượt xem")

    ListHorizontalVue(name="Yêu thích", nameNumber="lượt thích")

    ListHorizontalVue(name="Theo dõi nhiều", nameNumber="lượt theo dõi")

</template>

<!-- JAVASCRIPT -->
<script>
import ListHorizontalVue from './ListHorizontal.vue'
import sample_story from '@/assets/sample_story.jpg'

export default {
    components: {
        ListHorizontalVue,
        sample_story,
    }
}
</script>

<!-- STYLUS (css) -->
<style lang="stylus">
.body-part-2
    width: 65%
    display: flex
    margin: 0 auto

</style>