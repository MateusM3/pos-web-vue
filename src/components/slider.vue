<template>
  <div>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      img-height="480"
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <!-- Text slides with image -->
      <b-carousel-slide
        caption="First slide"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
        img-src="https://http2.mlstatic.com/god-war-ps4-D_NQ_NP_806531-MLB27539367851_062018-F.jpg"
        width="1024"
        height="480"
      ></b-carousel-slide>

      <b-carousel-slide
        img-src="https://http2.mlstatic.com/console-nintendo-switch-pokemon-lets-go-pikachu-bundle-D_NQ_NP_746788-MLB29129565950_012019-F.jpg"
        width="1024"
        height="480"
      >
      </b-carousel-slide>

    </b-carousel>
    <br>
    <br>
  </div>
</template>


<script>
  export default {
    data() {
      return {
        slide: 0,
        sliding: null
      }
    },
    methods: {
      onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      }
    }
  }
</script>
