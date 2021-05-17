<template>
  <div class="teitimonial mb-10  ">
    <div class="xl:grid xl:grid-cols-2">
      <div class="left pb-5">
        <div class="shape relative">
          <img :src="item.shape" alt="" class="w-2/3" />
          <p
            class="absolute top-2/4 transform translate-x-5 -translate-y-3/4 text-24 leading-7 text-black-01 w-full xl:translate-x-20"
          >
            {{ item.review }}
          </p>
        </div>
        <div class="avatar">
          <img
            :src="item.avatar"
            alt=""
            class="ml-auto transform -translate-y-4 w-1/3 -translate-x-1/4"
          />
        </div>
      </div>
      <div class="right pt-10 border-t-2 border-white xl:border-t-0 xl:border-l-2 xl:pl-12">
        <h5 class="title font-bold mb-5">{{ item.title }}</h5>
        <p class="mb-10">{{ item.description }}</p>
        <p class="mb-10">{{ item.span }}</p>
        <img :src="item.footer" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },
  },
};
</script>

<style>
</style>