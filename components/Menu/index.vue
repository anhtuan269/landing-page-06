<template>
  <div class="menu relative "
  >
      <div class="icon cursor-pointer" @click="mobile"> 
          <img src="@/static/image/menu.svg" alt="">
      </div>
      <div class="main-menu absolute top-10 right-0 bg-white p-10 rounded-at shadow-at  w-250 h-n-350 duration-500 ease-in-out transform  "
      :class="tab"
      >
        <ul >
          <li  v-for="(item,index) in menu" :key="index" class="pb-5">
            <nuxt-link :to="item.link">
             <div class="flex items-center">
               <div class="icon">
                 <img :src="item.icon" alt="">
               </div>
               <div class="text ml-5">
                 <p>{{item.text}}
                   <span>{{item.span}}</span>
                 </p>
               </div>
             </div>
            </nuxt-link>
          </li>
        </ul>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return{
      menu:[],
      moblie_menu:false
    }
  },
  async fetch() {
    this.menu = await fetch('http://localhost:3000/menu').then((res) => {
      return res.json()
    })
  },
  methods:{
    mobile() {
      return this.moblie_menu = !this.moblie_menu
    }
  },
  computed: {
    tab() {
      if(this.moblie_menu === true) {
        return 'opacity-1 translate-x-0 '
      }else {
        return 'opacity-0 translate-x-2/4'
      }
    }
  }

}
</script>

<style scoped>

.menu.mobile .main-menu {
  opacity: 1;
}

</style>