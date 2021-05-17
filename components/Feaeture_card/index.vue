<template>
  <div class="feature_card text-center mt-12 md:text-left">
      <div class="card">
          <div class="icon mb-5">
              <img :src="item.icon" alt="" class="mx-auto md:mr-auto md:mx-0">
          </div>
          <h4 class="text-black font-semibold mb-3 xl:text-20 ">{{item.title}}</h4>
          <p class="w-250 mx-auto mb-5 leading-6 md:mr-auto md:mx-0 xl:w-200 xl:text-18">{{item.description}}</p>
          <div class="link font-bold text-brown leading-6 hover:text-blue-01 duration-500 ease-linear cursor-pointer">
              <p>{{item.link}}</p>
          </div>
      </div>
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