<template>

    <v-container fluid>
        <toolbar />
        <v-row class="sin_margin">
             <div style="margin-top: 1em; ">
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
                :to="'/sandwiches'"
                small
              >
                  Sándwiches 
              </v-chip>
              <p style="color: orange; font-weigth: 800; display:inline; margin-left: 0 !important"> /  </p>

              <v-chip
                class="ma-2"
                color="primary"
                text-color="white"
                :to="'/sandwiches'"
                small
              >
                  Veggie
              </v-chip>
            </div>
            <v-col cols="12" :class="`rounded-t-xl` "  class="text-center text-no-wrap secondary margin justify-center align-center"></v-col>
            
            <v-row class="margin_img justify-center" >
             
                <v-img src="/images/productos/sandwiches/veggie.png" max-width="200"  height="200" ></v-img>
            
            <v-container>
                <h3 class="text-center white--text mt-3"> Tostado veggie </h3>
                 <v-rating
                        :value="3"
                        color="white"
                        dense
                        hover
                        half-increments
                        background-color="white"
                        size="10"
                        class="text-center"
                      ></v-rating>

                        <p class="white--text comentarios solo-numeros"> (230) </p>
            </v-container>
                <p class="parrafos"> Tostado con palta, queso, pepinos y tomates cherrys. Perfecta combinación de sabores.Para compartir.</p>

                <p class="parrafos"> Ingredientes:  palta, queso, pepinos y tomates cherrys, pan y jamón. </p>


            
                <v-col cols="6">
                  <v-btn id="aumentar" v-on:click="aumentar" x-small>+</v-btn>
                       <input type='text' id="cantidad" value="0" class="white--text solo-numeros">                 
                  <v-btn id ="disminuir" v-on:click="disminuir" x-small>-</v-btn>

                </v-col>
                
                <v-col cols="6">
                        <div class="text-right" style="width: 80%">
                            <p class="text-right white--text precio solo-numeros"> $100 </p>
                        </div>  
                </v-col>

                 <v-btn class="font-weight-semibold primary text-capitalize margin_puntos " elevation="0" rounded @click="overlay = !overlay" > 
                  Agregar al carrito
                </v-btn>

                  <v-overlay :value="overlay">
                      <v-alert
                        v-model="alert"
                        light
                        elevation="2"
                        class="position">
                        <v-icon color="green" x-small>mdi-check-circle</v-icon>
                            El producto ha sido agregado al carrito
                            <v-btn 
                            small
                            rounded 
                            to="carrito"
                            class="text-center primary text-capitalize font-weight-normal justify-content-right button_alert"> 
                            <v-icon> mdi-cart-outline </v-icon>
                            Ver carrito 
                            </v-btn>
                        </v-alert>
                  </v-overlay>

            
            
            </v-row>

            
            
         
        </v-row>

        
    </v-container>

 
   
</template>

<script>
export default {
    data: () => ({
      overlay: false,
      inicio: 0,
    }),
        watch: {
            overlay (val) {
                val && setTimeout(() => {
                this.overlay = false
                
                }, 30000)
            },
        },
     methods: {
         aumentar: function() {
             var cantidad = document.getElementById('cantidad').value = ++this.inicio;
          
         },

         disminuir: function() {
             var cantidad = document.getElementById('cantidad').value = --this.inicio;

         }

         
     }
}

</script>

<style>

*  {
      font-family: 'Raleway', sans-serif ;
    }

.solo-numeros {
    font-family: 'Montserrat', sans-serif;
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
    font-weight: 200;
    text-align: left;
    margin-top: 1em;
    width: 90%;

}

.v-alert:not(.v-sheet--tile) {
     border-radius: 30px;
}

.position{
    top: -220px;
    right: 0;
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
        font-weight: 600;
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
        font-size: 14 px !important;
    }

 }


</style>