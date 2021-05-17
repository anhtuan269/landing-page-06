<template>
  <div class="hero max-w-400 mx-auto my-20 md:max-w-2xl xl:max-w-1200 xl:flex  xl:justify-between xl:my-28">
    <div class="content">
      <Heading
      v-for="(head, index) in heading"
      :key="index"
      v-show="head.type === 'hero'"
      :head="head"
      :section="head.type"
    />
    <Button
      class="my-10"
      v-for="(button, index) in buttons"
      :key="index"
      v-show="button.type === 'free'"
      :button="button"
      :background="button.background"
    />
    <div class="app">
      <h3 class="text-14 font-bold text-black mb-5">Or download the app:</h3>
      <div class="content flex items-center">
        <App
          class="mr-6 mb-20"
          v-for="(item, index) in app"
          :key="index"
          v-show="item.type === 'hero'"
          :item="item"
        />
      </div>
    </div>
    </div>
    <div class="image">
      <img src="@/static/image/hero.png" alt="" class="w-full" />
    </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Button from "@/components/Button";
import App from "@/components/App_image";
import Image from "@/components/Image";
export default {
  components: {
    Heading,
    Button,
    App,
    Image,
  },
  data() {
    return {
      heading: [],
      buttons: [],
      app: [],
      // section:'hero'
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.buttons = await fetch("http://localhost:3000/button").then((res) => {
      return res.json();
    });
    this.app = await fetch("http://localhost:3000/app").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>