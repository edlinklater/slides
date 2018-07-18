<template lang='pug'>
.frontpage
  .content
    h1
      span slides
      span.grey .ed.geek.nz

    .thumbnails
      .box-card(v-for='slideshow in slideshows')
        router-link(:to='slideshow.infos.path' @click.native="click")
          .embedded-slideshow-container
            component(:is="slideshow", :embedded='true',
                      :keyboardNavigation='false',
                      :mouseNavigation='false')
        .caption
          h3 {{slideshow.infos.title}}
          p.thumbnail-description {{slideshow.infos.description}}
</template>

<script>
import slideshows from 'slideshows/slideshows'

export default {
  data: function () {
    return {
      slideshows: slideshows.list
    }
  },
  mounted: function () {
    document.currentSlide = {}
  },
  methods: {
    click: function (evt) {
      evt.stopPropagation()
    }
  }
}
</script>

<style lang='scss' scoped>
@import url('https://fonts.googleapis.com/css?family=Cabin');

.frontpage {
  width: 100%;
  height: auto;
  position: absolute;
  font-weight: normal;
  font-family: 'Cabin', sans-serif;

  .content {
    width: 800px;
    max-width: 90%;
    margin: 0 auto;
  }
}

h1 {
  font-size: 5em;
  margin: 0.5em 0;
  text-align: center;
}

h2 {
  font-size: 3.5em;
}

h3 {
  font-size: 2em;
}

p {
  margin-top: 1.5em;
  font-size: 23px;
}

.grey {
  color: #bbb;
}

.box-card {
  text-align: center;
  margin-bottom: 50px;

  .embedded-slideshow-container {
    position: relative;
    width: 150px;
    height: 120px;
    margin: 0 auto;
    border: 1px solid grey;
    overflow: hidden;
  }

  h3, p {
    margin-bottom: 0;
    margin-top: 0;
  }
}

a {
  text-decoration: inherit;
  color: inherit;
}
</style>
