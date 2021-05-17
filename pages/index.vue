
<template>
<div id="landing-page-06" >
  <Header />
  <Hero />
  <Feature />
  <Slide />
  <Game />
  <Feature2 />
  <Testimonial />
  <Statistical />
  <Ready />
  <Footer />
</div>
 
</template>

<script>
import Header from '@/components/Section/Header'
import Hero from '@/components/Section/Hero'
import Feature from '@/components/Section/Feature'
import Slide from '@/components/Section/Slide'
import Game from '@/components/Section/Game-area'
import Feature2 from '@/components/Section/Feature_work'
import Testimonial from '@/components/Section/Tesytimonial_slide'
import Statistical from '@/components/Section/Statis'
import Ready from '@/components/Section/Ready'
import Footer from '@/components/Section/Footer'
export default {
  components: {
    Header,
    Hero,
    Feature,
    Slide,
    Game,
    Feature2,
    Testimonial,
    Statistical,
    Ready,
    Footer
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

</style>