<template>
   <v-container>
       <v-row>
           
           <v-col  xs="12" sm="4">
           
                    <v-btn text color="orange" class="font-weight-semibold" @click="dialog=true"> 
                        Cerrar sesión
                    </v-btn>
               
        </v-col>
            
     
        
                <v-dialog v-model="dialog" width="500"  transition="dialog-bottom-transition"  persistent>
                    <v-card >
                        <v-img  src="/images/cerrar_sesion.png" ></v-img>
                        <v-card-title class="font-weight-regular justify-center align-center text-center pt-0" >
                           ¿Estás seguro de cerrar sesión?
                        </v-card-title>
                    
                        <v-card-actions class=" justify-center align-center pb-6 pt-0">
                            <v-btn  class="font-weight-semibold boton pa-4 text-capitalize"  elevation="6" rounded @click="dialog=false"> 
                                Cancelar
                            </v-btn>
                            <v-btn class="font-weight-semibold primary pa-4 text-capitalize" elevation="6" rounded @click="dialog=false"> 
                                Salir
                            </v-btn>

                        </v-card-actions>
                     </v-card>
                </v-dialog>


        </v-row>
    </v-container>
</template>

<script>
    export default {
         data(){
            return{
                dialog: false,
            }
    }
    }
</script>

<style lang="scss" scoped>
.v-card__title {
    word-break: normal; 
}


</style>