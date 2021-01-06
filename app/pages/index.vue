<template>
  <v-row class="customize_background">
    <v-col>
      <div class="text-center">
       <coffeaLogo />
      </div>
    </v-col>
  </v-row>
</template>

<script>
import CoffeaLogo from '~/components/CoffeaLogo.vue'



export default {
  components: {
    CoffeaLogo
  }

  
}

</script>


<style scoped>
  .customize_background {
    background-size: cover;
    background-color: #F8744E;
    height: 100%;
  }

</style>
