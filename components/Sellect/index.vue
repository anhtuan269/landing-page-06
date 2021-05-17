<template>
  <div class="sellect hidden">
      <div class="form">
          <select name="" id="">
              <option :value="item.text"> {{item.text}}</option>
              <option :value="item.text"> {{item.text_2}}</option>
          </select>
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