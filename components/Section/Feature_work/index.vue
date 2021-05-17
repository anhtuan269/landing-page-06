<template>
  <div class="feature mt-20 max-w-400 mx-auto md:max-w-2xl xl:max-w-1200">
    <Title
      v-for="(item, index) in title"
      :key="index"
      v-show="item.type === 'work'"
      :item="item"
    />
    <div class="content md:mt-20">
      <div class="item1 flex justify-between flex-col mb-20 md:flex-row xl:justify-center">
        <img src="@/static/image/feature-3.png" alt="" class="md:w-2/4 xl:w-440" />
        <Heading
          class="text-center mt-10 md:w-250 xl:ml-20 xl:w-310"
          v-for="(head, index) in heading"
          :key="index"
          v-show="head.type === 'create'"
          :head="head"
          :section="head.type"
        />
      </div>
      <div class="item1 flex justify-between flex-col-reverse mb-20 md:flex-row-reverse xl:justify-center">
        <img src="@/static/image/feature-2.png" alt="" class="md:w-7/12 xl:w-440" />
        <Heading
          class="text-center mb-10  xl:mr-20 xl:w-310"
          v-for="(head, index) in heading"
          :key="index"
          v-show="head.type === 'share'"
          :head="head"
          :section="head.type"
        />
      </div>
      <div class="item1 flex  justify-between flex-col mb-20 md:flex-row xl:justify-center">
        <img src="@/static/image/feature.png" alt="" class="md:w-7/12 xl:w-440" />
        <Heading
          class="text-center mt-10 md:w-250  xl:ml-20 xl:w-310"
          v-for="(head, index) in heading"
          :key="index"
          v-show="head.type === 'play'"
          :head="head"
          :section="head.type"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Title from "@/components/Special_title";
import Image from "@/components/Image/index";
import Heading from "@/components/Heading";
export default {
  components: {
    Title,
    Image,
    Heading,
  },
  data() {
    return {
      title: [],
      heading: [],
      image: [],
    };
  },
  async fetch() {
    this.title = await fetch("http://localhost:3000/special_heading").then(
      (res) => {
        return res.json();
      }
    );
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.image = await fetch("http://localhost:3000/image").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>