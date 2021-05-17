<template>
  <div class="footer bg-blue-01 p-10 text-center xl:text-left">
    <div
      class="max-w-400 mx-auto text-white md:max-w-2xl xl:max-w-1200 xl:flex xl:justify-between xl:items-center"
    >
      <div class="left mb-20 xl:w-3/12">
        <Logo
          class="xl:w-200"
          v-for="(item, index) in logo"
          :key="index"
          v-show="item.type === 'white'"
          :item="item"
        />
        <div class="app mt-10">
          <h3 class="font-bold text-12 leading-4">Get the app::</h3>
          <div
            class="flex justify-between items-center mt-5 md:max-w-400 md:mx-auto xl:grid xl:grid-cols-2"
          >
            <App
              class="w-5/12 xl:w-full"
              v-for="(item, index) in app"
              :key="index"
              v-show="item.type === 'footer'"
              :item="item"
            />
          </div>
        </div>
        <div class="social my-10">
          <h5>Follow us:</h5>
          <div class="flex items-center justify-center xl:justify-start mt-5">
            <Social v-for="(item, index) in social" :key="index" :item="item" />
          </div>
        </div>
      </div>
      <div class="right xl:w-8/12">
        <div class="grid grid-cols-2 md:grid-cols-4">
          <div
            class="item text-left mb-10 justify-self-center md:justify-self-start"
          >
            <Title
              v-for="(item, index) in title"
              :key="index"
              v-show="item.type === 'about'"
              :item="item"
            />
            <Item
              v-for="(item, index) in menu"
              :key="index"
              v-show="item.type === 'about'"
              :item="item"
            />
          </div>
          <div
            class="item text-left mb-10 justify-self-center md:justify-self-start"
          >
            <Title
              v-for="(item, index) in title"
              :key="index"
              v-show="item.type === 'Solutions'"
              :item="item"
            />
            <Item
              v-for="(item, index) in menu"
              :key="index"
              v-show="item.type === 'Solutions'"
              :item="item"
            />
          </div>
          <div
            class="item text-left mb-10 justify-self-center md:justify-self-start"
          >
            <Title
              v-for="(item, index) in title"
              :key="index"
              v-show="item.type === 'Resources'"
              :item="item"
            />
            <Item
              v-for="(item, index) in menu"
              :key="index"
              v-show="item.type === 'Resources'"
              :item="item"
            />
          </div>
          <div
            class="item text-left mb-10 justify-self-center md:justify-self-start"
          >
            <Title
              v-for="(item, index) in title"
              :key="index"
              v-show="item.type === 'Terms'"
              :item="item"
            />
            <Item
              v-for="(item, index) in menu"
              :key="index"
              v-show="item.type === 'Terms'"
              :item="item"
            />
            <div class="image xl:flex items-center">
              <img src="@/static/image/micro.png" alt="" class="mr-auto mb-5 xl:mb-0 xl:mr-1" />
              <img src="@/static/image/partner.png" alt="" class="mr-auto" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <Copy v-for="(item, index) in copy" :key="index">
      <p class="text-white">{{ item.text }}</p>
    </Copy>
  </div>
</template>

<script>
import Logo from "@/components/Logo";
import App from "@/components/App_image";
import Social from "@/components/Socail";
import Item from "@/components/Footer_menu";
import Title from "@/components/Footer_title";
export default {
  components: {
    Logo,
    App,
    Social,
    Item,
    Title,
  },
  data() {
    return {
      logo: [],
      app: [],
      social: [],
      title: [],
      menu: [],
      copy: [],
    };
  },
  async fetch() {
    this.logo = await fetch("http://localhost:3000/logo").then((res) => {
      return res.json();
    });
    this.social = await fetch("http://localhost:3000/social").then((res) => {
      return res.json();
    });
    this.app = await fetch("http://localhost:3000/app").then((res) => {
      return res.json();
    });
    this.menu = await fetch("http://localhost:3000/footer_text").then((res) => {
      return res.json();
    });
    this.title = await fetch("http://localhost:3000/footer").then((res) => {
      return res.json();
    });
    this.copy = await fetch("http://localhost:3000/copy").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>