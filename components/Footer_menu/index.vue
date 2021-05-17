<template>
  <ul class="content">
    <li class="py-1 transform hover:translate-x-5 duration-500 ease-linear">
      <nuxt-link
        class="hover:text-yellow-01 transform  duration-300 ease-linear font-medium text-14"
        :to="item.link"
        >{{ item.text }}</nuxt-link
      >
    </li>
  </ul>
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