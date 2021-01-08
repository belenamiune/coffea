<template>
    <v-container fluid>
        <navbar />
           <v-img src="https://cdn.vuetifyjs.com/images/toolbar/map.jpg" height="350px" class="img_margin"></v-img>
        <v-row>
            <v-col class="margin">
                <v-expansion-panels>
                        <v-expansion-panel
                            v-for="item in items"
                            :key="item.title"
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

                                
                                <v-row>
                                    
                                        <v-col> 
                                        <v-list-item-icon class="mr-4">
                                            <v-img src="/images/iconos/sucursal.svg"  ></v-img>
                                            </v-list-item-icon>    
                                        {{ item.title }}
                                        </v-col>
                                </v-row>
                                
                            </v-expansion-panel-header>

                            <v-expansion-panel-content>
                            

                                <v-list >
                                    
                                <v-list-item>
                                            <v-list-item-icon class="mr-4">
                                                <v-img src="/images/iconos/direccion.svg"  ></v-img>
                                            </v-list-item-icon>

                                            <v-list-item-content >
                                                <v-list-item-subtitle>{{ item.direccion }}</v-list-item-subtitle>
                                            </v-list-item-content>
                                </v-list-item>


                                <v-list-item>
                                            <v-list-item-icon class="mr-4">
                                                <v-img src="/images/iconos/telefono.svg"  ></v-img>
                                            </v-list-item-icon>

                                            <v-list-item-content >
                                                <v-list-item-subtitle>{{ item.telefono }}</v-list-item-subtitle>
                                            </v-list-item-content>
                                </v-list-item>


                                <v-list-item>
                                            <v-list-item-icon class="mr-4">
                                                <v-img src="/images/iconos/reloj.svg"  ></v-img>
                                            </v-list-item-icon>

                                            <v-list-item-content >
                                                <v-list-item-subtitle>{{ item.horario }}</v-list-item-subtitle>
                                            </v-list-item-content>
                                </v-list-item>
                                    
                                    
                                    
                                    
                                    </v-list>


                                </v-expansion-panel-content>
                        </v-expansion-panel>
                </v-expansion-panels>
            
        
            </v-col>
        </v-row>
    </v-container>
 
</template>

<script>

export default {
   
   data () {
      return {
        items: [
          { title: 'Sucursal Independencia', direccion: 'Independencia 664', telefono: '035115507456', horario: 'Lunes a viernes de 9 a 21 hs' },
          { title: 'Sucursal Blvd. San Juan', direccion: 'Boulevard San Juan 798', telefono: '0351548932', horario: 'Lunes a viernes de 9 a 21 hs'},
          { title: 'Sucursal Catamarca', direccion: 'Catamarca 247', telefono: '0351789835', horario: 'Lunes a lunes de 9 a 21 hs' },
          { title: 'Sucursal Isabel la Católica', direccion: 'Isabel la Católica 123', telefono: '03519873245', horario: 'Lunes a sábados de 9 a 21 hs' },
        ],
        right: null,
      }
    },
    
}
</script>


<style lang="css">


.img_margin {
    padding: 0 !important;
    margin: 0 !important;
}

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon {
    color:white;
    bottom: 1px;
}

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon::before {
    color:white;
    bottom: 1px;
}

button.v-expansion-panel-header--active{
      background-color:none !important;
      border-style: solid;
      border-color: #FFB29E;
      
  }

.v-list-item{
    padding: 0;
}

.v-list-item__title{
    font-size: 13px;
}

.v-list-item__subtitle{
    font-size: 13px;
}

.margin {
    margin-top: 3em;
}

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon {
    color: #FFB29E;
}

@media screen and (max-width: 320px) {


.v-expansion-panel-content__wrap {
    padding: 0 12px 16px !important;
}

}
</style>