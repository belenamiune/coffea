<template>
   <v-container>
        <toolbar />
       <v-row class="justify-center align-center mt-16 ">
           <v-avatar size="205" color="#EFEFEF">
            <v-avatar size="190" color="primary">
                <v-avatar size="180" color="#EFEFEF">
                        <v-avatar size="150">
                                    <img src="https://randomuser.me/api/portraits/women/26.jpg">
                        </v-avatar>
                </v-avatar>
            </v-avatar>
           </v-avatar>
       </v-row>

       <v-row class="justify-center align-center mt-7"><h1 class="font-weight-semibold">Sofía Benza</h1> </v-row>
       
        <v-expansion-panels class="mt-10">
                    <v-expansion-panel
                    v-for="item in items"
                    :key="item.nro_pedido"
                    link
                    class="mb-5 pa-2 " 
                    :class="`rounded-lg`"
                    >
                        <v-expansion-panel-header >

                            <template v-slot:actions>

                            <v-avatar  color="primary" class="ml-2" size="19">
                                    <span class="white--text headline font-weight-bold "><v-icon class="icon">$expand</v-icon> </span>
                            </v-avatar> 

                            </template> 

                            <v-img src="/images/iconos/reserva.svg" max-width="25" class="mr-3 " ></v-img>
                            
                            <v-row>
                                
                            <v-col >Reserva</v-col>
                                <v-col class="text-right"> {{ item.nro_pedido }}</v-col>
                            </v-row>
                            
                        </v-expansion-panel-header>

                        <v-expansion-panel-content>
                        

                            <v-list class="mb-n3" >
                                
                                    <v-list-item>
                                        <v-list-item-icon class="mr-4">
                                            <v-img src="/images/iconos/personas.svg" width="25"></v-img>
                                        </v-list-item-icon>

                                        <v-list-item-content >
                                            <v-list-item-title>{{ item.personas }} personas</v-list-item-title>
                                        </v-list-item-content>
                                    </v-list-item>

                                    <v-list-item>
                                        <v-list-item-icon class="mr-4">
                                            <v-img src="/images/iconos/calendario.svg"  ></v-img>
                                        </v-list-item-icon>

                                        <v-list-item-content >
                                            <v-list-item-title>{{ item.fecha }}</v-list-item-title>
                                        </v-list-item-content>
                                    </v-list-item>

                                    <v-list-item>
                                        <v-list-item-icon class="mr-4">
                                            <v-img src="/images/iconos/reloj.svg" ></v-img>
                                        </v-list-item-icon>

                                        <v-list-item-content >
                                            <v-list-item-title >{{ item.hora }}</v-list-item-title>
                                        </v-list-item-content>
                                    </v-list-item>


                                    <v-list-item>
                                        <v-list-item-icon class="mr-4">
                                            <v-img src="/images/iconos/sucursal.svg" ></v-img>
                                        </v-list-item-icon>

                                        <v-list-item-content >
                                            <v-list-item-title> {{ item.sucursal }}</v-list-item-title>
                                        </v-list-item-content>
                                    </v-list-item>
                                

                                <v-list-item @click="dialog=true" >
                                    <v-list-item-icon class="mr-4 mb-0 mt-3">
                                    <v-img  src="/images/iconos/delete.svg"></v-img>
                                    </v-list-item-icon>
                                    
                                    <v-list-item-content >
                                        <v-list-item-title style="color:red"> Eliminar reserva</v-list-item-title>
                                    </v-list-item-content>
                                    </v-list-item>
                                
                                
                                </v-list>


                        </v-expansion-panel-content>
                    </v-expansion-panel>
                </v-expansion-panels>
            

            <v-dialog v-model="dialog" width="500"  transition="dialog-bottom-transition" >
                    <v-card persistent>
                        
                        <v-card-title class="font-weight-regular justify-center align-center text-center pt-8" >
                                ¿Estás seguro de cancelar esta reserva?
                        </v-card-title>
                    
                        <v-card-actions class=" justify-center align-center pb-6 pt-5" >
                            <v-btn class="font-weight-semibold boton pa-4 custom-transform-class text-none"  elevation="6" rounded @click="dialog=false"> 
                                No
                            </v-btn>
                            <v-btn class="font-weight-semibold primary pa-4 custom-transform-class text-none" elevation="6" rounded @click="eliminarTarea(index)"> 
                               Si
                            </v-btn>

                        </v-card-actions>
                     </v-card>
                </v-dialog>

                <v-row  class="justify-center align-center text-center" >
                    <v-btn class="font-weight-semibold primary justify-center align-center pa-4 mt-12 custom-transform-class text-none " elevation="6" rounded to="reservas"> 
                         Reservar
                    </v-btn>

                 </v-row>

   </v-container>
</template>

<script>

export default {
    
     data () {
         // v-for="items in 1" :key="items"
        return {
        items: [
            {
            nro_pedido: '01',
            personas:'3',
            fecha: '10 de abril del 2021',
            hora: '16:30',
            sucursal: 'Independencia  664',
            },
            /**{
            nro_pedido: '02',
            personas:'8',
            fecha: '6 de enero del 2021',
            hora: '18:30',
            sucursal: 'Isabel la católica 123',
            },
            {
            nro_pedido: '01',
            personas:'6',
            fecha: '28 de diciembre del 2020',
            hora: '10:00',
            sucursal: 'Independencia  664',
            },**/

        ],
         dialog: false,}
    },

    methods:{
         eliminarTarea(index){
                 this.items.splice(index, 1);

            if(this.items == 0) {
                   window.location.href = 'sin_reservas';
            }     
        },
    }
}
</script>

<style lang="scss" scoped>

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon {
    color:white;
   bottom: 1px;
}


button.v-expansion-panel-header--active{
      background-color:none !important;
      border-style: solid;
     border-color: #F8744E;
     border-radius:10px;
     margin: 0;
  }

.v-list-item{
    padding: 0;
}

.v-list-item__title{
    font-size: 13px;
    color: black;
    
}

h1{
    font-size: 22px;
    color: black;
}

.col{
    color: black;
}

.v-dialog > .v-card > .v-card__title {
    word-break: normal; 
    font-size: 18px;
}


*{
  font-family: 'rawline', sans-serif !important; 
  color: black;
}

.montserrat{
  font-family: 'Montserrat', sans-serif;
}

.margin{
    margin-top:50px;
}
</style>