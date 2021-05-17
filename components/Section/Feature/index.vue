<template>
  <div class="feature p-10 bg-gray-02 mb-20 md:px-10 py-20 ">
    <div class="max-w-400 mx-auto md:max-w-2xl xl:max-w-1200">
      <Title
        v-for="(item, index) in title"
        :key="index"
        v-show="item.type === 'who'"
        :item="item"
      />
      <div class="feature-center md:grid md:grid-cols-2 md:transform md:translate-x-4 xl:grid-cols-4">
        <Card
          class="justify-self-center "
          v-for="(item, index) in card"
          :key="index"
          v-show="item.type === 'school'"
          :item="item"
        />
        <Card
          class="justify-self-center"
          v-for="(item, index) in card"
          :key="index"
          v-show="item.type === 'work'"
          :item="item"
        />
        <Card
          class="justify-self-center"
          v-for="(item, index) in card"
          :key="index"
          v-show="item.type === 'home'"
          :item="item"
        />
        <Card
          class="justify-self-center"
          v-for="(item, index) in card"
          :key="index"
          v-show="item.type === 'apps'"
          :item="item"
        />
      </div>
      <Button
        class="text-center mt-10"
        v-for="(button, index) in buttons"
        :key="index"
        v-show="button.type === 'now'"
        :button="button"
      />
    </div>
  </div>
</template>

<script>
import Title from "@/components/Special_title";
import Card from "@/components/Feaeture_card";
import Button from "@/components/Button";
export default {
  components: {
    Title,
    Card,
    Button,
  },
  data() {
    return {
      title: [],
      card: [],
      buttons: [],
    };
  },
  async fetch() {
    this.title = await fetch("http://localhost:3000/special_heading").then(
      (res) => {
        return res.json();
      }
    );
    this.card = await fetch("http://localhost:3000/feature_card").then(
      (res) => {
        return res.json();
      }
    );
    this.buttons = await fetch("http://localhost:3000/button").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>