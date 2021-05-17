<template>
  <div class="social mr-5">
      <img :src="item.url" alt="">
  </div>
</template>

<script>
export default {
    props: {
        item: {
            type:Object
        }
    }

}
</script>

<style>

</style>