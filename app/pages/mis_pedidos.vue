<template>
<v-container>
     <v-row>
            <v-col cols="12" :class="`rounded-t-xl` "  class=" text-center text-no-wrap primary margin justify-center align-center" >
            
            </v-col>

            <v-row class="margin_img justify-center" >
                <v-img src="/images/mis_pedidos.png" max-width="300"  height="100%" ></v-img>
            </v-row>
            
            
            <v-expansion-panels style="margin-top: 130px; " class="pa-3">

                <v-expansion-panel
                 v-for="item in items"  :key="item.nro_pedido"  link    class="mb-5 pa-2 "  :class="`rounded-lg`">
                    <v-expansion-panel-header >

                        <template v-slot:actions>

                        <v-avatar  color="primary" class="ml-2" size="19">
                                <span class="white--text headline font-weight-bold "><v-icon class="icon">$expand</v-icon> </span>
                        </v-avatar> 

                        </template> 

                        <v-img src="/images/iconos/cafe.svg" max-width="25" class="mr-3 mt-n2" ></v-img>
                        
                        <v-row>
                            
                        <v-col> Pedido</v-col>
                            <v-col class="text-right"> {{ item.nro_pedido }}</v-col>
                        </v-row>
                        
                    </v-expansion-panel-header>

                    <v-expansion-panel-content>
                    

                        <v-list >
                            
                                <v-list-item>
                                    <v-list-item-icon class="mr-4">
                                        <v-img src="/images/iconos/estado.svg"   ></v-img>
                                    </v-list-item-icon>

                                    <v-list-item-content >
                                        <v-list-item-title> Estado del pedido</v-list-item-title>
                                    </v-list-item-content>
                                </v-list-item>

                                <v-list-item class="mt-n5">
                                <v-progress-linear color="secondary" :value='item.progreso' rounded > </v-progress-linear>
                                </v-list-item>
                            
                                <v-list-item>
                                    <v-list-item-icon class="mr-4">
                                        <v-img src="/images/iconos/reloj.svg"  ></v-img>
                                    </v-list-item-icon>

                                    <v-list-item-content >
                                        <v-list-item-title> Tiempo estimado</v-list-item-title>
                                        <v-list-item-subtitle>{{ item.tiempo }}</v-list-item-subtitle>
                                    </v-list-item-content>
                                </v-list-item>

                                <v-list-item>
                                    <v-list-item-icon class="mr-4">
                                        <v-img src="/images/iconos/sucursal.svg" ></v-img>
                                    </v-list-item-icon>

                                    <v-list-item-content >
                                        <v-list-item-title> Sucursal a cargo</v-list-item-title>
                                        <v-list-item-subtitle>{{ item.sucursal }}</v-list-item-subtitle>
                                    </v-list-item-content>
                                </v-list-item>


                                <v-list-item>
                                    <v-list-item-icon class="mr-4">
                                        <v-img src="/images/iconos/direccion.svg" ></v-img>
                                    </v-list-item-icon>

                                    <v-list-item-content >
                                        <v-list-item-title> Dirección de envio</v-list-item-title>
                                        <v-list-item-subtitle>{{ item.direccion }}</v-list-item-subtitle>
                                    </v-list-item-content>
                                </v-list-item>
                            

                            <v-list-item>
                                <v-list-item-icon class="mr-4">
                                    <v-img src="/images/iconos/detalle.svg"  ></v-img>
                                </v-list-item-icon>
                                
                                <v-list-item-content >
                                    <v-list-item-title style="color:#184042"> Detalle de compra</v-list-item-title>
                                </v-list-item-content>
                                </v-list-item>
                            
                            
                            </v-list>


                    </v-expansion-panel-content>
                </v-expansion-panel>
            </v-expansion-panels>
            
        </v-row>

</v-container>
</template>

<script>
export default {
    data () {
        return {items: [
        {
          nro_pedido:'03',
          progreso:70,
          tiempo: '17:30-17:50',
          sucursal: 'Independencia  664',
          direccion:'Espora 2053',
          detalle_de_compra:'',
        },
        {
          nro_pedido:'02',
          progreso:100,
          tiempo: '10:20-10:40',
          sucursal: 'Isabel la católica 123',
          direccion:'Vieytes 1800',
          detalle_de_compra:'',
        },
        {
          nro_pedido:'01',
          progreso:100,
          tiempo: '21:00-21:40',
          sucursal: 'Independencia  664',
          direccion:'Yrigoyen 2600',
          detalle_de_compra:'',
        },

        ]
       }
    }
}
</script>

<style lang="scss" scoped>


.margin{
    position:absolute;
    top:200px;
    left:0px;
    bottom: 0;
    z-index:1;
  
}

.margin_img{
    position:relative;
    top:80px;
    z-index:2;}

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon {
    color:white;
   bottom: 1px;
}


button.v-expansion-panel-header--active{
    background-color:none !important;
    border-style: solid;
    border-color: #FFB29E;
    border-radius:10px;
    margin: 0;
  }



.v-list-item__title{
    font-size: 13px;
}

.v-list-item__subtitle{
    font-size: 13px;
}

</style>