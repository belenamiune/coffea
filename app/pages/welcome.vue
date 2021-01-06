<template>
      <v-row justify="center customize_background" align="center"> 
         <v-col cols="12" sm="12" justify ="center">
            <header>
               <img src="../static/images/logo-circulo.svg"> 
            </header>

                     <div class="text center">
                           <div class="my-2">
                                 <v-btn
                                    v-bind="attrs"
                                    v-on="on"
                                    class="text-center text-capitalize my-2"
                                    style="width:150px"
                                    color="primary"
                                    rounded
                                    to="/register_form"

                                 >
                                    Registrarse
                                 </v-btn>

                           </div>

                           <div class="my-2">
                                 <v-btn
                                    v-bind="attrs"
                                    v-on="on"
                                    class="text-center text-capitalize my-2"
                                    style="width:150px; color: #F8744E "
                                    color="white"
                                    rounded
                                    to= "/login"

                                 >
                                    Iniciar sesión
                                 </v-btn>

                           </div>


                     </div>

                </v-col>
          </v-row>
       
</template>

<script>
  
  export default {

  }

</script>

<style scoped>

   .customize_background {

      background-size: cover;
      background-image: url('../static/images/background.png');
      height: 100%;
   }

   * {
      text-align: center !important;
      font-family: 'Raleway', sans-serif;;
   }

 

</style>

