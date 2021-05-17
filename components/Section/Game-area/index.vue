<template>
  <div class="gam_center text-center">
    <Heading class="mb-10"
      v-for="(head, index) in heading"
      :key="index"
      v-show="head.type === 'game'"
      :head="head"
      :section="head.type"
    />
    <div class="bg-yellow-01 py-28 text-center">
      <Logo class="mx-auto mb-10"
        v-for="(item, index) in logo"
        :key="index"
        v-show="item.type === 'white'"
        :item="item"
      />
      <div class="content relative w-330  mx-auto" v-for="(item, index) in input" :key="index">
        <input type="text" class="px-10 py-3 rounded-at-02 font-bold focus:outline-none" :placeholder="item.placeholder" />
        <div class="svg absolute right-0 transform  translate-y-3 top-0">
          <img :src="item.url" alt="" class="w-9/12" />
        </div>
        <span class="try block text-gray-01 mt-4">{{ item.try }}</span>
      </div>
    </div>
    <div class="more mt-5" v-for="(item, index) in input" :key="index">
      <h2 class="text-24 mx-auto max-w-400 leading-7 xl:max-w-1200 ">
        {{ item.more }}
        <span class="text-blue-01 cursor-pointer hover:text-yellow-01 duration-500 ease-linear font-bold">{{ item.take }}</span>
      </h2>
    </div>
  </div>
</template>

<script>
import Logo from "@/components/Logo/index";
export default {
  components: {
    Logo,
  },
  data() {
    return {
      logo: [],
      input: [],
      heading: [],
    };
  },
  async fetch() {
    this.input = await fetch("http://localhost:3000/game_center").then(
      (res) => {
        return res.json();
      }
    );
    this.logo = await fetch("http://localhost:3000/logo").then((res) => {
      return res.json();
    });
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>