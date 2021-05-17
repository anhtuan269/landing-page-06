<template>
  <div class="title mb-5">
      <h2 class="text-28 font-bold text-center leading-8 mb-2 xl:text-36 xl:leading-44 "
      :class="black"
      >{{item.title}}</h2>
      <div class="bottom w-100 h-2 mx-auto"
      :class="white"
      ></div>
  </div>
</template>

<script>
export default {
    props: {
        item:{
            type: Object
        },
        color: String
    },
    computed: {
        white() {
            if(this.color==='custom'){
                return 'bg-white'
            } else {
                return 'bg-blue-01'
            }
        },
        black() {
            if(this.color==='custom') {
                return 'text-white'
            } else {
                return 'text-black-01'
            }
        }
    }

}
</script>

<style>

</style>