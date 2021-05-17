<template>
  <div class="card relative">
    <div class="image w-full">
      <figure class="w-full">
        <img :src="item.url" alt="" class="w-full h-n-240 md:h-full" />
      </figure>
    </div>
    <div class="content absolute top-10 left-8 md:top-20 md:left-10" :class="color">
      <span class="text-white rounded-at-02 px-5 py-2 text-20 font-bold leading-6"
      :class="background"
      >{{ item.new }}</span>
      <h3 class="title my-3 text-24 font-bold leading-6 md:w-250 md:leading-8">{{ item.title }}</h3>
      <p class="description mb-3 text-18 leading-6 md:w-350 ">{{ item.description }}</p>
      <p class="link font-bold text-18 leading-6 duration-500 ease-linear hover:text-yellow-01 cursor-pointer  ">{{ item.link }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },
    text: String,
    id:Number
  },
  computed: {
    color() {
      if (this.text === "white") {
          return 'text-white'
      } else {
          return 'text-black-01'
      }
    },
    background() {
        if( this.id===3) {
            return 'bg-black-01'
        } else if ( this.id === 4) {
            return 'bg-yellow-01'
        } else if(this.id === 5) {
            return 'bg-green-01'
        } else {
            return ' '
        }

    }
  },
};
</script>

<style scoped>
</style>