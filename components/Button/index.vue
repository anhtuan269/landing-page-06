<template>
  <div class="button ">
    <button class="px-10 py-3 font-extrabold text-14 leading-4 xl:text-16"
    :class="backgroundColor"
    >{{ button.text }}</button>
  </div>
</template>

<script>
export default {
  props: {
    button: {
      type: Object,
      default() {
        return {
          text: "login",

        };
      },
      background:{
        type:String
      }
    },
  },
  computed: {
    backgroundColor() {
      if (this.background === 'white') {
        return 'bg-white text-gray-01 hover:bg-yellow-01 duration-500 ease-linear '
      } else {
        return 'bg-blue-01 text-white hover:bg-yellow-01 duration-500 ease-linear'
      }

    }
  }
};
</script>

<style>
</style>