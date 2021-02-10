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
                    <p class="mt-8">Mi compra</p>
               </v-col>
                <v-col cols="2">
                    <p style="font-family:'Montserrat', sans-serif" class="p_style ml-3"><img  src="../static/images/iconos/puntos_blanco.svg" class="puntos_img">600</p>
                    <p style="font-family:'Montserrat', sans-serif;  font-weight: bold;" class="ml-3"><img  src="../static/images/iconos/puntos_blanco.svg" class="puntos_img">650</p>
               </v-col>
               <v-col cols="12"  style="margin-top: -1em" >
                    <hr />
               </v-col>
               <v-row  class="margin_img justify-center align-center delivery mb-3" style="color:white;">
                <v-col cols="10">
                    <p>Puntos que faltan</p>
                    <p style="font-weight: 100; font-size:10px; word-break: break-all">Podes completar tu compra con diferentes medios de pago. Se descontarán tus puntos una vez finalizada la compra. </p>
               </v-col>
                <v-col cols="2" class="puntos_finales2">
                    <p style="font-family:'Montserrat', sans-serif;  font-weight: bold;" class="ml-1"><img  src="../static/images/iconos/puntos_blanco.svg" class="puntos_img_2">50</p>
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
                        style="height: 36px !important; width: 160px"
                      >
                      
                       Canjear
                      </v-btn>

                       <v-btn
                        class="mr-4 text-center custom-transform-class text-none btn_cancel"
                        rounded
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
                            
                            <v-row class="justify-content-center mt-5 row_buttons">
                                <v-btn 
                                   normal
                                    rounded 
                                     @click="overlay = false"
                                     class="text-center custom-transform-class text-none font-weight-normal cancel_button ma-1"> 
                                        No
                                </v-btn>
                                <v-btn 
                                    normal
                                    rounded 
                                    class="text-center primary custom-transform-class text-none font-weight-normal  ma-1"> 
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
                        class="position">
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

                        <v-dialog v-model="dialog" width="500"  transition="dialog-bottom-transition"  class="dialogo mx-0"  overflow-hidden full-screen persistent>
                             <v-card class=" justify-center align-center text-center">
                                    <v-btn
                                        icon
                                        small
                                        color="black"
                                        class="cerrar mt-2 mr-2"
                                        @click="dialog=false"
                                    >
                                            
                                    <v-icon>mdi-close</v-icon>
                                                
                                    </v-btn>
                                            
                                    <v-card-title class="px-12 mb-4 mt-3">
                                         <p>Tus puntos son insuficientes.
                                         Te faltan <strong style="font-family: 'Montserrat', sans-serif">$45 </strong> para terminar la compra. </p>

                                        <p style="font-size: 20px"> ¿Querés completar el pago con dinero? </p>
                                    </v-card-title>
                                
                                 
                                    <v-card-actions class=" justify-center align-center text-center"> 
                                        <v-btn color="secondary" class="secondary custom-transform-class text-none" to="detalles_puntos"> 
                                            <v-img src="/images/iconos/en_mano.svg" class="mr-2" max-width="20"></v-img>
                                           Si, quiero completar
                                        </v-btn>
                                     </v-card-actions>

                              
                                <v-card-actions class=" justify-center align-center text-center"> 
                                    <v-btn color="secondary" class="secondary custom-transform-class text-none"  to="home" > 
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
                
                }, 30000)
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

.btn_cancel {
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

.v-alert:not(.v-sheet--tile) {
     border-radius: 30px;
}

.position{
    position: relative;
    top: -350px;
    right: 0;
}

.delivery { 
    max-width: 250px !important;
    margin-left: 0.5em;
}

.puntos_img {
  max-width: 30px;
  margin-left: -2em;
  margin-bottom: -2em;
}

.puntos_img_2 {
  max-width: 30px;
  margin-left: -2em;
  margin-bottom: -2em;
}

.p_style {
  margin-top: -1.5em;
  font-weight: bold;
}

.puntos_finales {
  margin-top: -4em;
}

.puntos_finales2 {
  margin-top: -5em;
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
    font-size: 16px;
    top: 75px;
}

.cancel_button {
    background-color: transparent;
    border: 1px solid #F8744E;
    color: #F8744E !important;
    margin-left: -2em;
}

.row_buttons {
    justify-content: center !important;
}

.v-sheet.v-card{
    border-radius:10px;
}

input{
    width: 25px;
}


.v-card__subtitle, .v-card__text, .v-card__title{
    padding: 8px;
}

.v-img{
 max-height:100px;
}

.precio{
    padding-top: 0;
}
.cerrar{
   // margin-left: 17px;
   position: absolute;
   right: 5px;
}

.v-chip.v-size--default{
    width: 93%;
     border-style: solid;
    border-color: black;
    border-width: 1px;
    color: black;
}

.aclaracion{
    color: #878686;
    font-size: 15px;
    position: absolute;
    right: 9%;
}

.boton_comprar{
    position: absolute;
}


.v-dialog > .v-card{
   border-radius: 30px 30px 0px 0px;
    position: absolute;
    left:0;
    bottom: 0;
    height: 60%;
}
.v-dialog > .v-card > .v-card__title {
    word-break: normal; 
    font-size: 14px;
}

.v-card__actions > .v-btn.v-btn{
    width: 80%;
    border-radius: 10px;
    height: 45px;
}


@media screen and (min-width: 375px) {
    .v-img{
        max-height: 200px;
    }

    .precio{
         padding-top: 10px;
    }

    .cerrar{
     margin-left: 47px;
}

}


</style>