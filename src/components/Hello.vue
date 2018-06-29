<template>
  <div class="container">
    <b-carousel id="carousel1"
                style="text-shadow: 1px 1px 2px #333; max-width=100% important!;"
                controls
                indicators
                background="#ababab"
                :interval="4000"
                img-width="1024"
                img-height="480"
                v-model="slide"
                @sliding-start="onSlideStart"
                @sliding-end="onSlideEnd"
    >

      <div v-for="picture in this.pictures" :key="picture.id">
        <b-carousel-slide>
          <img slot="img" class="d-block img-fluid w-100" width="500" height="200"
             :src="picture.url" alt="image slot">
        </b-carousel-slide>
      </div>

    </b-carousel>
  </div>
</template>

<script>
const mock_data = [
  {
    url: "https://picsum.photos/1024/480/?image=54",
    cap: "First slide",
    text: "Nulla vitae elit libero, a pharetra augue mollis interdum."
  },
  {
    url: "https://picsum.photos/1024/480/?image=58",
    cap: "2nd slide",
    text: "Nulla vitae elit libero, a pharetra augue mollis interdum."
  },
  {
    url: "https://picsum.photos/1024/480/?image=52",
    cap: "3rd slide",
    text: "Nulla vitae elit libero, a pharetra augue mollis interdum."
  },
  {
    url: "https://picsum.photos/1024/480/?image=55",
    cap: "4th slide",
    text: "Nulla vitae elit libero, a pharetra augue mollis interdum."
  },
]
export default {
  data () {
    return {
      slide: 0,
      sliding: true,
      pictures: mock_data
    }
  },
  methods: {
    onSlideStart (slide) {
      this.sliding = true
    },
    onSlideEnd (slide) {
      this.sliding = true
    }
  }
}
</script>