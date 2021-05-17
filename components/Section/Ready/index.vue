<template>
  <div class="ready max-w-400 mx-auto items-center justify-between text-center mb-20 flex flex-col-reverse md:max-w-2xl md:flex-row xl:max-w-1200" >
    <div class="image mt-20 md:mt-0">
      <img src="@/static/image/ready.png" alt="" class="w-11/12"/>
    </div>
    <div class="heading md:text-left xl:w-680">
      <Heading
        v-for="(head, index) in heading"
        :key="index"
        v-show="head.type === 'footer'"
        :head="head"
        :section="head.type"
      />
      <Button
        v-for="(button, index) in buttons"
        :key="index"
        v-show="button.type === 'free'"
        :button="button"
      />
    </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Button from "@/components/Button";
export default {
  components: {
    Heading,
    Button,
  },
  data() {
    return {
      heading: [],
      buttons: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.buttons = await fetch("http://localhost:3000/button").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>