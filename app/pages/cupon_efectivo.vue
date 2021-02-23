<template>
        <div class="background_image">
             <img src="../static/images/logo-circulo.svg" width="100px" class="image_resize"> 
           <v-container fluid>
                 <toolbar />
              <v-row>
                  <v-col  :class="`rounded-t-xl`"  class="mt-3 mb-6 pa-20 text-center text-no-wrap white margin justify-center align-center" >
                
                        
                  
                            <h2 class="mt-8"> Cupón de pago </h2>
                                
                                <v-container>
                                    <v-row>
                                        <v-col cols xs="6">
                                
                                         <p class="text-center mb-8 mt-4">El siguiente código QR será escaneado cuando asistas a cualquiera de nuestras sucursales por un período de<strong style="font-family:'Montserrat', sans-serif"> 24hs. </strong></p>
                            
                                        </v-col>
                                    </v-row>
                                </v-container>

                                <img src="../static/images/qr-code.svg" width="150px"> 
                            <v-container>
                                <v-row>
                                    <v-col>
                                        <v-btn
                                            class="mr-4 mt-6 text-center custom-transform-class text-none"
                                            @click="submit"
                                            color="primary"
                                            rounded
                                            to="/detalle_tradicional_sucursal"
                                        >
                                            
                                           Confirmar compra
                                        </v-btn>

                                        </v-col>
                                </v-row>
                            </v-container>
                        
                </v-col>
            </v-row>
        </v-container>
                       
    </div>

</template>

<script>
    
  export default {
    
        
        }   

    
    </script>

    <style lang="scss" scoped>

    *  {
          font-family: 'Raleway', sans-serif ;
      }


        .margin{
            position: absolute;
            top: 100px;
            left:0px;
            z-index: 2;
            bottom: 0; 
        }

        .background_image {
            background-image: url('../static/images/background.png');
            background-size: cover;
            padding: 2em;
        }

        .image_resize {
            margin-top: -25px;
        }

         h2 {
            font-weight: normal;
        }


        p {

            white-space:pre-wrap !important;
        }

        .v-btn {
            font-weight: normal;
        }        
    </style>