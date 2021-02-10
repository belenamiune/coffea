<template>

    <v-container fluid>
        <toolbar />
        <v-row class="sin_margin justify-center align-center text-center">
             <div style="margin-top: 2em; ">
              <v-chip
                class="ma-2"
                color="primary"
                text-color="white"
                :to="'/categorias'"
                small
              >
        
                  Categorías
              </v-chip>

                    <p style="color: orange; font-weigth: 800; display:inline; margin-left: 0 !important"> /  </p>
             
              <v-chip
                class="ma-2"
                color="primary"
                text-color="white"
                :to="'/cafe'"
                small
              >
                  Café 
              </v-chip>
              <p style="color: orange; font-weigth: 800; display:inline; margin-left: 0 !important"> /  </p>

              <v-chip
                class="ma-2"
                color="primary"
                text-color="white"
                :to="'/categorias'"
                small
              >
                  Café italiano
              </v-chip>
            </div>
            
            <v-col cols="12" :class="`rounded-t-xl` "  class="text-center text-no-wrap secondary margin justify-center align-center"></v-col>
            
            <v-row class="margin_img justify-center" >
             
                <v-img src="/images/productos/cafe/italiano.png" max-width="200"  height="200" ></v-img>
            
                <v-container>
                    <h3 class="text-center white--text mt-3"> Café italiano </h3>
                    <v-rating
                            :value="4"
                            color="white"
                            dense
                            hover
                            half-increments
                            background-color="white"
                            size="15"
                            class="text-center"
                        ></v-rating>

                            <p class="white--text comentarios solo-numeros"> (165) </p>
                </v-container>

                <p class="parrafos font-weight-semibold"> Café tostado más intenso que proporciona un sabor profundo, dulce y acaramelado, con baja acidez. </p>

                <p class="parrafos font-weight-semibold"> Cantidad:  <span class="solo-numeros"> 300 ml </span> </p>

                <p class="parrafos font-weight-semibold">Ingredientes: leche y café. </p>

            
                <v-col cols="6"  class="pl-3">
                   <v-btn id ="disminuir" v-on:click="value--" outlined color="white" x-small style="font-size:25px;" class="pb-1">-</v-btn>
                        <input type='text' id="cantidad" :value="Math.abs(value)" class="solo-numeros white--text" >
                    <v-btn id="aumentar" v-on:click="value++" x-small color="white" style="font-size:25px;color:#184042"  elevation="0">+</v-btn>
                </v-col>
                
                <v-col cols="6">
                        <div class="text-right" style="width: 80%">
                            <p class="text-right white--text precio solo-numeros"> $80 </p>
                        </div>  
                </v-col>

                 <v-btn class="font-weight-semibold primary custom-transform-class text-none margin_puntos " elevation="0" rounded @click="overlay = !overlay" > 
                  Agregar al carrito
                </v-btn>
                </v-row>

                
                  <v-overlay :value="overlay">
                      <v-alert
                        v-model="alert"
                        light
                        elevation="2"
                        class="position">
                        <v-icon color="green" dense>mdi-check-circle</v-icon>
                            El producto ha sido agregado al carrito
                            <v-btn 
                            small
                            rounded 
                            to="carrito"
                            class="text-center primary custom-transform-class text-none font-weight-normal justify-content-right button_alert"> 
                            <v-icon dense> mdi-cart-outline </v-icon>
                            Ver carrito 
                            </v-btn>
                        </v-alert>
                  </v-overlay>

            
            
            

            
            
         
        </v-row>

        
    </v-container>

 
   
</template>

<script>
export default {
    data: () => ({
      overlay: false,
       value: 0,
    }),
        watch: {
            overlay (val) {
                val && setTimeout(() => {
                this.overlay = false
                
                }, 4000)
            },
        },
         
     }


</script>

<style>

 * {
        font-family: 'Raleway', sans-serif;
    }


.margin {
    position: fixed;
    top:200px;
    left:0px;
    z-index:1;
    bottom: 0;
    
}

.margin_img {
    position:relative;
    top:40px;
    z-index:2;
    margin: 0 !important;
    
}


div.container {
    padding: 0;
}


.parrafos {
    color: white;
    font-size:14px;
    text-align: left;
    margin-top: 1em;
    width: 85%;

}

.v-alert:not(.v-sheet--tile) {
     border-radius: 30px !important;
}

.position{
    top: -220px;
    right: 7.5%;
    text-align: left;
    justify-content: right;
    font-size: 13px;
}

.button_alert {
     margin-left: 10em;
     margin-top: 2em;
   
}

.v-btn--icon.v-size--default {
       width: 50%;
}

.solo-numeros {
    font-family: 'rawline', sans-serif !important; 
}

 @media screen and (min-width: 320px) {
    
    
   .imagen2 {
        max-width: 200px !important;
        max-height: 200px !important;
        position: inherit
    }

    .sin_margin {
        
        margin: 0 !important;
    }


    .precio {
        font-size: 24px;
        font-weight: 500;
    }

    #cantidad {
        width: 20%;
        text-align: center;
    }

    
    .margin {
         margin-bottom: -4em;
    
    }

    .comentarios {
        margin-top: -1.7em !important;
        margin-right: 8em !important;
        text-align: right;
        font-size: 12px;

    }

    .v-rating {
        margin-left: -0.5em !important;
    }

    div.container {
        padding-top: 0.2em !important;
    }

    .v-alert {
        margin-left: 3em !important;
        font-size: 14px !important;
    }

 }


</style>