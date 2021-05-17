<template>
    <div class="app-image">
        <img :src="item.url" alt="" class="mb-5">
    </div>
</template>

<script>
export default {
    props: {
        item:{
            type:Object
            
            
        }
    }

}
</script>

<style>

</style>