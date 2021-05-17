<template>
  <div class="testimonial bg-blue-01 py-20">
    <div class=" mx-auto max-w-400 text-white md:max-w-2xl xl:max-w-1200">
      <Title
        v-for="(item, index) in title"
        :key="index"
        v-show="item.type === 'custom'"
        :item="item"
        :color="item.type"
      />
      <div class="slide mt-10  ">
        <VueSlickCarousel v-bind="settings">
          <Testimonial
            v-for="(item, index) in slides"
            :key="index"
            :item="item"
          />
        </VueSlickCarousel>
      </div>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

import Title from "@/components/Special_title";
import Testimonial from "@/components/Testimonial";

export default {
  components: {
    Title,
    Testimonial,
    VueSlickCarousel,
  },
  data() {
    return {
      title: [],
      slides: [],
      settings: {
        dots: true,
        dotsClass: "slick-dots custom-dot-class",
        edgeFriction: 0.35,
        infinite: true,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
        arrows:false
      },
    };
  },
  async fetch() {
    this.title = await fetch("http://localhost:3000/special_heading").then(
      (res) => {
        return res.json();
      }
    );
    this.slides = await fetch("http://localhost:3000/testimonial_slide").then(
      (res) => {
        return res.json();
      }
    );
  },
};
</script>

<style>
</style>