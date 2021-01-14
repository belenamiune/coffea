<template>
  <div>
    <VueSlickCarousel :arrows="true" :dots="true" v-bind="settings">
      <v-img src="/images/home/cafe.svg"></v-img>
      <v-img src="/images/iconos/cafe.svg"></v-img>
      <v-img src="/images/iconos/cafe.svg"></v-img>
      <v-img src="/images/iconos/cafe.svg"></v-img>
      <v-img src="/images/iconos/cafe.svg"></v-img>
      <v-img src="/images/iconos/cafe.svg"></v-img>
      
    </VueSlickCarousel>
  </div>
</template>
 
<script>
  import VueSlickCarousel from 'vue-slick-carousel'
  import 'vue-slick-carousel/dist/vue-slick-carousel.css'
  // optional style for arrows & dots
  import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
 
  export default {
    name: 'MyComponent',
    components: { VueSlickCarousel },
    
    data() {
    return{
    settings:{
  "dots": true,
  "focusOnSelect": true,
  "infinite": true,
  "speed": 500,
  "slidesToShow": 3,
  "slidesToScroll": 3,
  "touchThreshold": 5,
    }
}}}
</script>

<style lang="scss" scoped>

</style>