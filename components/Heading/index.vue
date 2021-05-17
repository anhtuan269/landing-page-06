<template>
  <div class="heading">
      <h2 class=" font-bold"
      :class="title"
      >
      <span class="block">{{head.span}}</span>
      {{head.title}}</h2>
      <p class=""
      :class="content"
      >{{head.description}}</p>
  </div>
</template>

<script>
export default {
    props: {
        head: {
            type: Object,
            
        },
        section:{
            type:String
        }
    },
    computed:{
        title() {
            if(this.section ==='hero') {
                return ' text-42 text-black-01 leading-l-50  mb-10 xl:text-74 xl:leading-l-100'
            } else if( this.section ==='footer') {
                return 'text-42 text-black-01 leading-l-50  mb-10 xl:text-74 xl:leading-l-100'
            }
            else {
                return 'text-28 text-black-01 mb-2 text-36 leading-l-44'
            }
        },
        content() {
             if(this.section ==='hero') {
                return ' text-20     text-brown leading-l-22 xl:text-24 xl:leading-l-40 xl:w-400'
            } else {
                return 'xl:text-20 leading-l-22'
            }
        }
    }

}
</script>

<style>

</style>