<template>
  <div class="statis max-w-400 mx-auto my-20 md:max-w-2xl xl:max-w-1200">
  <div class="md:grid md:grid-cols-2 xl:grid-cols-4">
     <Statistical
      class="justify-self-center"
      v-for="(item,index) in statis" :key="index" :item="item" :color="item.color"/>
  </div>
  </div>
</template>

<script>
import Statistical from '@/components/Statistical'
export default {
  components: {
    Statistical
  },
  data() {
      return {
        statis:[]
      }
  },
  async fetch() {
    
     this.statis = await fetch("http://localhost:3000/statical").then(
      (res) => {
        return res.json();
      }
    );
  },
};
</script>

<style>
</style>