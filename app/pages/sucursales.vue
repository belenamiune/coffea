<template>
    <v-container>
    <div id ="app">
        <navbar />
         <Map />
    </div>
    
    <v-container fuild justify="center">
        <v-row justify="center">
            <v-col cols md= "12" class="margin" >
                <v-expansion-panels 
                        class="mb-5 pa-2 rounded-lg " 
                        accordion 
                        v-for="item in items"
                        :key="item.title">
                
                        <v-expansion-panel>
                              <v-expansion-panel-header> {{ item.title }} </v-expansion-panel-header>
                                <v-expansion-panel-content>
                                    <v-list-item>
                                        <v-list-item-content>
                                            <v-list-item-title> {{ item.direccion }}</v-list-item-title>
                                            <v-list-item-title> {{ item.telefono }}</v-list-item-title>
                                            <v-list-item-title> {{ item.horario }}</v-list-item-title>
                                        </v-list-item-content>
                                </v-list-item>
                                </v-expansion-panel-content>
                        </v-expansion-panel>
                            
                     
    
                
                </v-expansion-panels>

              </v-col>
          </v-row>

    </v-container>
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

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon {
    color:white;
    bottom: 1px;
}


button.v-expansion-panel-header--active{
      background-color:none !important;
      border-style: solid;
      border-color: #FFB29E;
      margin: 0;
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
    margin-top: 23em;
}

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon {
    color: orange;
}

</style>