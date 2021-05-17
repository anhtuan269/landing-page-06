<template>
  <div class="header pt-10 flex justify-between items-center max-w-400 mx-auto md:max-w-2xl xl:max-w-1200" >
    <Logo v-for="(item, index) in logo" :key="index"  :item="item" v-show="item.type==='black'" />
    <div class="left flex">
      <Sellect v-for="(item, index) in select" :key="index" :item="item" />
     <div class="hidden xl:flex xl:mr-5">
        <Button v-for="(button, index) in buttons" :key="index" :button="button" v-show="button.type=== 'up'"  class="mr-5"/>
      <Button v-for="(button, index) in  buttons" :key="index" :button="button" v-show="button.type=== 'in'" :background="button.background" />
     </div>
      <Menu v-for="(item, index) in logo" :key="index" v-show="item.type=== 'black'"/>
    </div>
  </div>
</template>

<script>
import Logo from "@/components/Logo/index";
import Sellect from "@/components/Sellect";
import Button from "@/components/Button";
import Menu from "@/components/Menu";
export default {
  components: {
    Logo,
    Sellect,
    Button,
    Menu,
  },
  data() {
      return {
          logo:[],
          select:[],
          buttons:[],
          menu:[],
      }
  },
  async fetch() {
      this.logo = await fetch('http://localhost:3000/logo').then((res) => {
          return res.json()
      });
      this.select = await fetch('http://localhost:3000/select').then((res) => {
          return res.json()
      });
      this.buttons = await fetch('http://localhost:3000/button').then((res) => {
          return res.json()
      });
      this.menu = await fetch('http://localhost:3000/menu').then((res) => {
          return res.json()
      });   
  },
  computed: {
      
  }
};
</script>

<style>
</style>