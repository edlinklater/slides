<template lang="pug">
  .eg-slideshow.somar
    img(src='/static/logo-vw.png')
    slide(enter='' leave='slideOutLeft').center
      h1 Welcome
    slide(enter='slideInRight' leave='slideOutLeft').center
      div
        h1 Intros
        h3 Who are we all?
    slide(enter='slideInRight' leave='slideOutLeft').center
      div
        h1 Show & Tell
    slide(enter='slideInRight' leave='slideOutLeft').center
      div
        h1 Future Meetups
        h3 Time/day? Format? Speakers?
    slide(enter='slideInRight' leave='slideOutLeft').center.white
      img(src='/static/vue-shirt.jpg' height='500' width='500' style='max-width: unset')
    slide(enter='slideInRight' leave='slideOutLeft').center
      h1 Q&A
    slide(enter='slideInRight' leave='slideOutLeft').center
      h1 Thanks for coming!
</template>

<script>
  import eagle from 'eagle.js'

  export default {
    mixins: [eagle.slideshow],
    infos: {
      title: 'Welcome to Wellington.vue',
      description: 'Wellington.vue Meetup, 18/07/2018',
      path: 'vue-2018-07-18'
    },
    data: function () {
      return {}
    }
  }
</script>

<style lang='scss'>
  @import '../../themes/somar/somar.scss';
</style>
