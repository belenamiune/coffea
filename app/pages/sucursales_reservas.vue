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
                            class="mb-3 pa-2 " 
                            :class="`rounded-lg`"
                            >

                            <v-expansion-panel-header >

                                <template v-slot:actions>

                                <v-avatar  color="primary" class="ml-2" size="19">
                                        <span class="white--text headline font-weight-bold "><v-icon class="icon">$expand</v-icon> </span>
                                </v-avatar> 

                                </template> 

                                
                                <v-row>
                                    
                                        <v-col cols="2"> 
                                        <v-list-item-icon class="mr-4" >
                                            <v-img src="/images/iconos/sucursal.svg"  ></v-img>
                                        </v-list-item-icon> 
                                        </v-col>  
                                        <v-col cols="10" class="mt-5"> 
                                        {{ item.title }}
                                        </v-col>
                                </v-row>
                                
                            </v-expansion-panel-header>

                            <v-expansion-panel-content>
                            

                                <v-list >
                                    
                                <v-list-item>
                                            <v-list-item-icon class="mr-4">
                                                <v-img src="/images/iconos/direccion.svg" max-width="20"></v-img>
                                            </v-list-item-icon>

                                            <v-list-item-content >
                                                <v-list-item-title class="solo-numeros ">{{ item.direccion }}</v-list-item-title>
                                            </v-list-item-content>
                                </v-list-item>


                                <v-list-item>
                                            <v-list-item-icon class="mr-4">
                                                <v-img src="/images/iconos/telefono.svg" max-width="20"></v-img>
                                            </v-list-item-icon>

                                            <v-list-item-content >
                                                <v-list-item-title class="solo-numeros">{{ item.telefono }}</v-list-item-title>
                                            </v-list-item-content>
                                </v-list-item>


                                <v-list-item>
                                            <v-list-item-icon class="mr-4">
                                                <v-img src="/images/iconos/reloj.svg" max-width="20"></v-img>
                                            </v-list-item-icon>

                                            <v-list-item-content >
                                                <v-list-item-title class="solo-numeros">{{ item.horario }}</v-list-item-title>
                                            </v-list-item-content>
                                </v-list-item>
                                    
                                    
                                    
                                    
                                    </v-list>


                                </v-expansion-panel-content>
                        </v-expansion-panel>
                </v-expansion-panels>
                <v-row style="justify-content:center">
                    <v-btn 
                        class="font-weight-semibold secondary justify-center align-center pa-4 mt-5 mb-10 margin_img margin custom-transform-class text-none" 
                        elevation="6" 
                        rounded
                        to="reservar" 
                        > 
                        Seleccionar sucursal
                        </v-btn>

                      
                </v-row>
        
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


<style lang="css" scoped>


*  {
      font-family: 'Raleway', sans-serif ;
    }


.solo-numeros {
     font-family: 'rawline', sans-serif !important; 
     font-size: 13px;
     color: black;
}

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
    margin-top: 2.8em;
}

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon {
    color: #FFB29E;
}

@media screen and (max-width: 320px) {


.v-expansion-panel-content__wrap {
    padding: 0 12px 16px !important;
}

}

* {
    font-family: 'Raleway', sans-serif;
}
.margin{
    position:absolute;
    top: 320px;
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

h1{
    font-size: 22px;
  
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
.cerrar {
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
    font-size: 20px;
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