<template>
  <div class="feature_slide max-w-400 mx-auto mb-20 md:max-w-2xl ">
    <Title
      v-for="(item, index) in title"
      :key="index"
      v-show="item.type === 'Amazing'"
      :item="item"
    />
    <div class="slide">
      <VueSlickCarousel v-bind="settings">
        <Slide
          v-for="(item, index) in card"
          :key="index"
          :item="item"
          :text="item.text"
          :id="item.id"
        />
      </VueSlickCarousel>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

import Title from "@/components/Special_title";
import Slide from "@/components/Image_card";
export default {
  components: {
    Title,
    Slide,
    VueSlickCarousel,
  },
  data() {
    return {
      title: [],
      card: [],
      settings: {
        dots: true,
        dotsClass: "slick-dots custom-dot-class",
        edgeFriction: 0.35,
        infinite: true,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
        responsive: [
          {
            breakpoint: 768,
            settings: {
              dots: true,
              dotsClass: "slick-dots custom-dot-class",
              edgeFriction: 0.35,
              infinite: true,
              speed: 500,
              slidesToShow: 1,
              slidesToScroll: 1,
              centerPadding:"20px"

            },
          },
          {
            breakpoint: 1280,
            settings: {
              dots: true,
              dotsClass: "slick-dots custom-dot-class",
              edgeFriction: 0.35,
              infinite: true,
              speed: 500,
              slidesToShow: 1,
              slidesToScroll: 1,
            },
          },
          {
            breakpoint: 1536,
            settings: {
              dots: true,
              dotsClass: "slick-dots custom-dot-class",
              edgeFriction: 0.35,
              infinite: true,
              speed: 500,
              slidesToShow: 1,
              slidesToScroll: 1,
              centerPadding:"20px"
            },
          },
          {
            breakpoint: 1536,
            settings: {
              dots: true,
              dotsClass: "slick-dots custom-dot-class",
              edgeFriction: 0.35,
              infinite: true,
              speed: 500,
              slidesToShow: 1,
              slidesToScroll: 1,
            },
          },
        ],
      },
    };
  },
  async fetch() {
    this.title = await fetch("http://localhost:3000/special_heading").then(
      (res) => {
        return res.json();
      }
    );
    this.card = await fetch("http://localhost:3000/feature_slide").then(
      (res) => {
        return res.json();
      }
    );
  },
};
</script>

<style scoped>
.slide .slick-slider .slick-dots li {
  background-color: #000;
}
</style>