<template>
  <div class="statistical mb-10 ">
      <div class="content border-l-4"
      :class="background">
          <p class="ml-3 font-extrabold leading-5 md:w-200">{{item.title}}</p>
      </div>
  </div>
</template>

<script>
export default {
    props: {
        item: {
            type:Object
        },
        color:String
    },
    computed: {
        background() {
            if(this.color==='blue'){
                return 'border-blue-01'
            } else if( this.color==='green') {
                return 'border-blue-02'
            } else if(this.color==='red') {
                return 'border-red-01'
            } else {
                return 'border-yellow-01'
            }
        }
    }

}
</script>

<style>

</style>