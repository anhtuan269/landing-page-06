<template>
  <div class="logo">
      <img :src="item.url" alt="" class="mx-auto">
  </div>
</template>

<script>
export default {
    props: {
        item: {
            type:Object,
            require:true,
            
        }
    }

}
</script>

<style>

</style>