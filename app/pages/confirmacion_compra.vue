<template>
        <div class="background_image" >
             <img src="../static/images/logo-circulo.svg" width="100px" class="image_resize"> 
           <v-container fluid >
              <v-row>
                  <v-col  :class="`rounded-t-xl`"  class="mt-5 mb-6 pa-20 text-center text-no-wrap white margin justify-center align-center" >

                        
                  
                            <h2> Compra confirmada </h2>
                                <v-container>
                                    <v-row>
                                        <v-col cols xs="6">
                                
                                         <p class="text-center mb-8 mt-8">La compra ha sido realizada exitosamente</p>
                            
                                        </v-col>
                                    </v-row>
                                </v-container>

                                <img src="../static/images/iconos/check.svg" width="150px"> 
                            <v-container>
                                <v-row>
                                    <v-col>
                                        <v-btn
                                            class="mr-4 mt-6 text-center custom-transform-class text-none"
                                            color="primary"
                                            rounded
                                           
                                            @click="overlay = !overlay; mandarPedidos ()"
                                        >
                                            
                                            Ver pedido
                                        </v-btn>

                                    </v-col>
                                </v-row>
                            </v-container>
                        

                            
                    </v-col>
              </v-row>

              <v-overlay :value="overlay">
                                <v-alert
                                    v-model="alert"
                                    light
                                    elevation="2"
                                    class="position">
                                     <img src="../static/images/iconos/puntos_naranja.svg" width="20px" class="mb-n1 mr-2"> 

                                       Se acreditaron <strong> 4 </strong> puntos en tu cuenta con tu última compra
                                        <v-btn 
                                        small
                                        rounded 
                                        to="mis_puntos"
                                        class="text-center primary text-capitalize font-weight-normal justify-content-right button_alert mt-4"> 
                                         <img src="../static/images/iconos/puntos_blanco.svg" width="20px" class="mr-1"> 
                                        Ver puntos
                                        </v-btn>
                                    </v-alert>
                            </v-overlay>
                       
         </v-container>
         
          </div>

          

</template>

<script>
    
    export default {
        data() {
          return {
            overlay:false,
         }
      },

         watch: {
        overlay (val) {
        val && setTimeout(() => {
             this.overlay = false;
            },8000);
        }
        },   

      methods:{
    
       mandarPedidos () {
            setTimeout(function(){
                 window.location.href = 'mis_pedidos';     
                    }, 3000);
        },
    }
    }

    

    
</script>

    <style lang="scss" scoped>

   .fade-enter-active, .fade-leave-active {
  transition: opacity .1000s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}



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
            margin-top: -20px;
        }

         h2 {
            margin-top: 15px;
            font-weight: normal;
        }


        p {

            white-space:pre-wrap !important;
        }

        .v-btn {
            font-weight: normal;
        }   

        .v-alert:not(.v-sheet--tile) {
            border-radius: 30px;
        }

        .position{
            width: 80%;
            top: -220px;
            left: 10%;
            text-align: left;
            justify-content: right;
            font-size: 13px;
        }

        .button_alert {
            margin-left: 10em;
        
        
        }

.v-btn--icon.v-size--default {
       width: 50%;
} 
    </style>