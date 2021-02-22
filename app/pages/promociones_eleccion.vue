<template>
    <v-container fluid>
      <toolbar />
            <v-row justify="center" class="text-center">

                <div class="text-left " style="margin-top: 2em; ">
                    <v-chip
                        class="ma-2"
                        color="primary"
                        text-color="white"
                        :to="'/promociones'"
                        small
                    >
                
                        Promociones
                    </v-chip>

                            <p style="color: orange; font-weigth: 800; display:inline; margin-left: 0 !important"> /  </p>
                    
                    <v-chip
                        class="ma-2"
                        color="primary"
                        text-color="white"
                        small
                    >
                       Meriendas
                    </v-chip>

        
                </div>
                
                <v-row justify="center" class="text-center mt-2 ma-5">
                    
                        <v-list subheader>
                            <v-subheader>Licuados </v-subheader>

                            <v-list-item
                                v-for="chat in licuados"
                                :key="chat.title"
                            >

                            <v-col cols="6">
                                <v-list-item-content class="text-align-left">
                                <v-list-item-title v-text="chat.title"></v-list-item-title>
                                </v-list-item-content>
                             </v-col>

                             <v-col cols="6">
                                <v-list-item-icon>
                                    <div class="button_cantidad">
                                        <v-btn id ="disminuir" v-on:click="chat.value--" outlined color="secondary" x-small style="font-size:25px;" class="pb-1">-</v-btn>
                                             <input type='text' id="cantidad" :value="Math.abs(chat.value)" class="solo-numeros" >
                                        <v-btn id="aumentar" v-on:click="chat.value++" x-small color="secondary" style="font-size:25px;"  elevation="0">+</v-btn>
                                  </div>
                                </v-list-item-icon>
                             </v-col> 
                            </v-list-item>
                        </v-list>
                </v-row>
                   
                   
                    
                 <v-row justify="center" class="text-center mt-2 ma-5">
                    
                        <v-list subheader>
                            <v-subheader> Tortas </v-subheader>

                            <v-list-item
                                v-for="chat in tortas"
                                :key="chat.title"
                            >

                                <v-col cols="6">
                                    <v-list-item-content class="text-align-left">
                                    <v-list-item-title v-text="chat.title"></v-list-item-title>
                                    </v-list-item-content>
                                </v-col> 

                                <v-col cols="6">
                                    <v-list-item-icon>
                                        <div class="button_cantidad">
                                            <v-btn id ="disminuir" v-on:click="chat.value--" outlined color="secondary" x-small style="font-size:25px;" class="pb-1">-</v-btn>
                                                 <input type='text' id="cantidad" :value="Math.abs(chat.value)" class="solo-numeros" >
                                            <v-btn id="aumentar" v-on:click="chat.value++" x-small color="secondary" style="font-size:25px;"  elevation="0">+</v-btn>
                                    </div>
                                    </v-list-item-icon>
                                </v-col> 

                            </v-list-item>
                        </v-list>
                    
                </v-row>

            
            </v-row>

            <v-row justify="center" class="text-center mt-8">
                    <v-col>

                <v-btn class="font-weight-semibold primary custom-transform-class text-none margin_puntos " elevation="0" rounded @click="overlay = !overlay"> 
                 Aceptar
                </v-btn>

                   <v-overlay :value="overlay">
                      <v-alert
                        v-model="alert"
                        light
                        elevation="2"
                        class="position">
                        <v-icon color="green" small>mdi-check-circle</v-icon>
                            El producto ha sido agregado al carrito
                            <v-btn 
                            small
                            rounded 
                            to="carrito"
                            class="text-center primary custom-transform-class text-none  font-weight-normal justify-content-right button_alert"> 
                            <v-icon> mdi-cart-outline </v-icon>
                            Ver carrito 
                            </v-btn>
                        </v-alert>
                  </v-overlay>
                    </v-col>
            </v-row>

    </v-container>

</template>


<script>

  export default {
    data: () => ({
         licuados: [
        {
        
          title: 'Banana',
          value:0,
        },
        {
         
          title: 'Frutilla',
          value:0,
        },
        {
         
          title: 'Durazno',
          value:0,
        },
        
      ],
      tortas: [
        {
         
          title: 'Selva negra',
          value:0,
        },
        {
        
          title: 'Marquise',
          value:0,
        },
        {
         
          title: 'Lemon pie',
          value:0,
        },
        {
         
          title: 'Carrot cake',
          value:0,
        },
        
      ],
      
      header: 'Promoción',
      overlay: false,
      inicio: 0,

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

<style scoped>

   * {
        font-family: 'Raleway', sans-serif;
    }


.col{
    padding: 0;
}

.v-container {
    padding: 0;
}

.v-subheader {
    font-size: 18px;
    font-weight: bold;
    color: #184042;
}

.v-list-item__content {
    text-align: left;
}

.v-list-item__icon {
    margin-left: 0 !important;
}

#cantidad {
        width: 20%;
        text-align: center;
    }
.button_cantidad {
    margin-right: -4em !important;
}


.v-alert:not(.v-sheet--tile) {
     border-radius: 20px;
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
    margin-top: 1em !important;  
}

.v-alert {
        margin-left: 3em !important;
        font-size: 14px !important;
    }

.v-btn--icon.v-size--default {
       width: 50%;
}

.solo-numeros {
     font-family: 'rawline', sans-serif !important;
}
 
 
    

</style>