<template>
    <v-container fluid>
      <toolbar />
            <v-row justify="center" class="text-center">

                <div class="text-left " style="margin-top: 1em; ">
                    <v-chip
                        class="ma-2"
                        color="primary"
                        text-color="white"
                        :to="'/categorias'"
                        x-small
                    >
                
                        Categorías
                    </v-chip>

                            <p style="color: orange; font-weigth: 800; display:inline; margin-left: 0 !important"> /  </p>
                    
                    <v-chip
                        class="ma-2"
                        color="primary"
                        text-color="white"
                        :to="'/promociones'"
                        x-small
                    >
                        {{ header }}
                    </v-chip>

                       <p style="color: orange; font-weigth: 800; display:inline; margin-left: 0 !important"> /  </p>
                    
                    <v-chip
                        class="ma-2"
                        color="primary"
                        text-color="white"
                        :to="'/promociones'"
                        x-small
                    >
                        Meriendas
                    </v-chip>
                </div>
                
                <v-row justify="center" class="text-center mt-2">
                    <v-col cols="12">
                        <v-list subheader>
                            <v-subheader>Licuados </v-subheader>

                            <v-list-item
                                v-for="chat in licuados"
                                :key="chat.title"
                            >

                                <v-list-item-content class="text-align-left">
                                <v-list-item-title v-text="chat.title"></v-list-item-title>
                                </v-list-item-content>

                                <v-list-item-icon>
                                    <div class="button_cantidad">
                                <v-btn id="aumentar" v-on:click="aumentar" x-small>+</v-btn>
                                     <input type='text' id="cantidad" value="0" >                 
                                 <v-btn id ="disminuir" v-on:click="disminuir" x-small>-</v-btn>
                                  </div>
                                </v-list-item-icon>
                                   
                            </v-list-item>
                        </v-list>

                   
                   
                    </v-col>

                    <v-col cols="12" >
                        <v-list subheader>
                            <v-subheader> Tortas </v-subheader>

                            <v-list-item
                                v-for="chat in tortas"
                                :key="chat.title"
                            >

                                <v-list-item-content class="text-align-left">
                                <v-list-item-title v-text="chat.title"></v-list-item-title>
                                </v-list-item-content>

                                <v-list-item-icon>
                                    <div class="button_cantidad">
                                <v-btn id="aumentar" v-on:click="aumentar" x-small>+</v-btn>
                                     <input type='text' id="cantidad" value="0" >                 
                                 <v-btn id ="disminuir" v-on:click="disminuir" x-small>-</v-btn>
                                  </div>
                                </v-list-item-icon>
                                   
                            </v-list-item>
                        </v-list>
                    </v-col>
                </v-row>

            
                </v-row>
            <v-row justify="center" class="text-center mt-8">
                    <v-col>

                <v-btn class="font-weight-semibold primary text-capitalize margin_puntos " elevation="0" rounded @click="overlay = !overlay"> 
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
                            class="text-center primary text-capitalize font-weight-normal justify-content-right button_alert"> 
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
        },
        {
         
          title: 'Frutilla',
        },
        {
         
          title: 'Duranzo',
        },
        
      ],
      tortas: [
        {
         
          title: 'Selva negra',
        },
        {
        
          title: 'Marquise',
        },
        {
         
          title: 'Lemon Pie',
        },
        {
         
          title: 'Carrot cake',
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

<style scoped>

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
 
    

</style>