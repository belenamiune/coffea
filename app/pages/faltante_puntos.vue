<template>
   <v-container fluid>
          <toolbar />
            <v-col cols="12" :class="`rounded-t-xl` "  class="text-center text-no-wrap secondary margin " > </v-col>

            <v-row  class="margin_img justify-center align-center delivery">
                <v-col class="text-center justify-center">
               <img src="../static/images/canje_puntos.png" class="delivery">
                </v-col>
            </v-row>
        
            <v-row  class="margin_img justify-center align-center delivery">
                <v-col class="text-left justify-left mb-3 mt-3">
                    <h3 style="color: white"> Compra con puntos </h3>
                    <hr  style="margin-top: 1em"  />
                </v-col>
            </v-row>
            <v-row class="margin_img justify-center align-center delivery" style="color:white">
               <v-col cols="10">
                    <p class="mb-4">Mis puntos disponibles</p>
               </v-col>
                <v-col cols="2" class="mt-n4">
                   <img  src="../static/images/iconos/puntos_blanco.svg" class="puntos_img"> <p style="font-family: 'rawline', sans-serif; font-weight: bold;" >7</p>
               </v-col>
               <v-col cols="10" class="mt-n10">
                    <p class="mt-8">Mi compra</p>
               </v-col>
                <v-col cols="2" class="mt-n10">
                   <img  src="../static/images/iconos/puntos_blanco.svg" class="puntos_img"> <p style="font-family: 'rawline', sans-serif;  font-weight: bold;" >8</p>
               </v-col>
               <v-col cols="12"  style="margin-top: -1em" >
                    <hr />
               </v-col>
               <v-row  class="margin_img justify-center align-center mb-3" style="color:white;">
                <v-col cols="10" class="ml-1">
                    <p>Puntos que faltan</p>
                    <p style="font-weight: 300; font-size:10px; word-break: normal">Podes completar tu compra con diferentes medios de pago. Se descontarán tus puntos una vez finalizada la compra. </p>
               </v-col>
                <v-col cols="2" class="puntos_finales ml-n3">
                    <img  src="../static/images/iconos/puntos_blanco.svg" class="puntos_img"><p style="font-family: 'rawline', sans-serif;  font-weight: bold;" >1</p>
               </v-col>
               
               </v-row>
            </v-row>

            <template>
                    <v-row
                      align="center"
                      justify="space-around"
                      class="margin_img justify-center align-center mt-14"
                    >
                      <v-btn
                        class="mr-4 text-center custom-transform-class text-none btn_confirm mb-2"
                        rounded
                        color="primary"
                        @click="overlay2 = !overlay2"
                        elevation="0"
                        style="height: 36px !important; width: 160px"
                      >
                      
                       Canjear
                      </v-btn>

                       <v-btn
                        class="mr-4 text-center custom-transform-class text-none btn_cancel"
                        rounded
                        elevation="0"
                        @click="overlay = !overlay"
                      
                      >
                      
                       Cancelar compra
                      </v-btn>

                       <v-overlay :value="overlay">
                      <v-alert
                        light
                        elevation="2"
                        class="position">
                            ¿Estás seguro de cancelar esta compra?
                            
                            <v-row class="justify-content-center justify-center align-center mt-5 row_buttons">
                                <v-btn 
                                   normal
                                    rounded 
                                     @click="overlay = false"
                                     elevation="0"
                                     class="text-center custom-transform-class text-none font-weight-normal cancel_button ma-1"> 
                                        No
                                </v-btn>
                                <v-btn 
                                    normal
                                    rounded 
                                    elevation="0"
                                    class="text-center primary custom-transform-class text-none font-weight-normal  ma-1"
                                     to="carrito"> 
                                         Si
                                </v-btn>
                            </v-row>
                        </v-alert>
                  </v-overlay>
                    </v-row>

                       <v-overlay :value="overlay2">
                      <v-alert
                        light
                        elevation="2"
                        class="position"
                       >
                            ¿Te quedaste sin puntos?
                            Podes completar tu compra con dinero. <br />
                            Presiona <v-btn 
                            x-small
                            rounded
                             @click="dialog=true"
                            class="text-center primary custom-transform-class text-none font-weight-normal justify-content-right button_alert"> 

                            Canjear
                            </v-btn> para continuar.
                        </v-alert>
                  </v-overlay>

                        <v-dialog v-model="dialog" width="500"  transition="dialog-bottom-transition"  class="dialogo mx-0"  overflow-hidden full-screen>
                             <v-card class=" justify-center align-center text-center">

                                 <v-col style="text-align: end">
                                    <v-btn
                                        icon
                                        small
                                        color="black"
                                        class="cerrar mt-2 mr-2"
                                        @click="dialog=false"
                                    >
                                            
                                    <v-icon>mdi-close</v-icon>
                                                
                                    </v-btn>
                                    </v-col>
                                            
                                    <v-card-title class="px-7 mb-2 mt-n3 justify-center align-center text-center" style="word-break: normal;font-family: 'rawline', sans-serif;">
                                         Tus puntos son insuficientes.
                                         Te faltan $30  para terminar la compra. 
                                    </v-card-title>
                                     <v-card-title class="px-7 mb-2 " style="word-break: normal">
                                        <p style="font-size: 20px; word-break: normal"> ¿Querés completar el pago con dinero? </p>
                                    </v-card-title>
                                
                                 
                                    <v-card-actions class=" justify-center align-center text-center"> 
                                        <v-btn color="secondary" class="secondary custom-transform-class text-none" to="forma_de_pago"> 
                                            <v-img src="/images/iconos/en_mano.svg" class="mr-2" max-width="20"></v-img>
                                           Si, quiero completar
                                        </v-btn>
                                     </v-card-actions>

                              
                                <v-card-actions class="justify-center align-center text-center"> 
                                    <v-btn color="secondary" class="secondary custom-transform-class text-none mb-2 "  to="home" > 
                                        <v-img src="/images/iconos/errorr.svg" class="mr-2" max-width="20"></v-img>
                                        No, cancelar compra
                                    </v-btn>
                                </v-card-actions>

                            </v-card>
                        </v-dialog>
                  </template>
               
   </v-container>
         

</template>

<script>
export default {
    data: () => ({
      overlay: false,
      overlay2: false,
      dialog: false,
    }),
        watch: {
            overlay (val) {
                val && setTimeout(() => {
                this.overlay = false
                
                }, 4000)
            },
        },
         watch: {
            overlay2 (val2) {
                val2 && setTimeout(() => {
                this.overlay2 = false
                
                }, 4000)
            },
        }
}

</script>

<style lang="scss" scoped>

* {
    font-family: 'Raleway', sans-serif;
}
.margin{
    position:absolute;
    top:200px;
    left:0px;
    bottom:0;
    height: 90%;
    padding-bottom: 0;
    z-index:1;
  
}

.margin_img{
    position: relative;;
    top:30px;
    bottom: 0;
    z-index:2;
}
.hr{
    width: 80% !important;
}
.btn_confirm{
     width: 60% !important;
}
.btn_cancel {
    width: 60%;
    color: #F8744E !important;
    background-color: transparent !important;
    border: 1px solid #F8744E;
}

.theme--light.v-label{
    color: white;
}

.v-text-field {
    border-radius:15px;
}

.v-label{
    padding-left: 8px;
}

.delivery { 
    max-width: 95% !important;
    margin-left: 2.5%;
}

.puntos_img {
  max-width: 30px;
  margin-left: -2em;
  margin-bottom: -2em;
}
.puntos_img1 {
  max-width: 30px;
  margin-bottom:-2em;
  margin-left:-2em;
}


.p_style {
  margin-top: -1.5em;
  font-weight: bold;
}

.puntos_finales {
  margin-top: -4em;
}

.v-alert:not(.v-sheet--tile) {
     border-radius: 20px;
}

.position {
    margin-right: 1em;
    margin-left: 1em;
    height: 8em;
    right: 0;
    text-align: center;
    justify-content: center;
    font-size: 13px;
    font-size: 16px;
}

.cancel_button {
    background-color: transparent;
    border: 1px solid #F8744E;
    color: #F8744E !important;
    margin-left: -2em;
}

.v-card:not(.v-sheet--tile) {
            border-radius: 30px;
        }

.v-card__actions > .v-btn.v-btn{
    width: 80%;
    border-radius: 10px;
    height: 45px;
}
</style>