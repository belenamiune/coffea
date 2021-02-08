<template>
   <v-container>
       <v-card 
            v-for="productos in productos"
            :key="productos.nombre" 
            class="color_card ml-3 mt-5 " 
            width="93%" >

            <v-row >

                <v-col cols="5" class="ml-n2 mr-0 mt-1">

                    <v-img
                        :src="productos.src" 
                    ></v-img>

                </v-col>

                <v-col cols="7" class="pl-0 ml-0 pt-0 " >
                    
                       
                     <v-card-title class="font-weight-semibold black--text pl-0" style="font-size:17px;">
                                {{ productos.nombre }}
                            
                      </v-card-title>
                    
                    <v-card-subtitle class="pb-0 font-weight-medium  black--text pl-0" style="font-size:12px;">
                        {{ productos.info }}
                    </v-card-subtitle>

                    

                    <v-card-text class="font-weight-medium text-right black--text precio" style="font-size:24px;" >$
                    {{productos.precio}}
                    </v-card-text>
                </v-col>

            </v-row>
        </v-card>

         <v-chip
        outlined
        class="mt-12 ml-3"
        >
        <v-row>
            <h3 class="ml-3">PUNTOS CANJEADOS</h3><img  src="../static/images/iconos/puntos_negro.svg" class="puntos_img "/><h3 class="cerrar1 mr-2"> 8</h3>
         </v-row>
        </v-chip>

         <v-chip
        outlined
        class="mt-1 ml-3"
        >
        <v-row>
            <h3 class="ml-3">TOTAL PAGADO </h3><h3 class="cerrar1 mr-2">$ 45</h3>
         </v-row>
        </v-chip>

    <v-row class=" justify-center align-center text-center mt-15">
        <v-btn class="font-weight-semibold secondary text-capitalize"  rounded  elevation="0"  @click="dialog=true" > 
                  Continuar
        </v-btn>
        </v-row>


   </v-container>
</template>

<script>
    export default {
        data: () => ({
      productos: [
        {
          nombre: 'Café italiano',
          src: '/images/productos/cafe/italiano.png',
          info:'300 ml',
          precio: 100,
          precio_suma:100,
          puntos:3,
          value:1,
        },

         {
          nombre: 'Tostado veggie',
          src: '/images/productos/sandwiches/veggie.png',
          info:'Unidad',
          precio: 100,
          precio_suma:100,
          puntos:3,
          value:1,
        },

        {
          nombre: 'Torta oreo',
          src: '/images/productos/tortas/oreo.png',
          info:'Porción',
          precio: 65,
          precio_suma:65,
          puntos:2,
          value:1,
        },
        ],
    }
    ),
    }
</script>

<style lang="scss" scoped>

.color_card{
    background-color:#F6F6F6 !important;  
}
.v-sheet.v-card{
    border-radius:10px;
}

.v-card__subtitle, .v-card__text, .v-card__title{
    padding: 8px;
}

.puntos_img {
  max-width: 23px;
 position: relative;
 left: 13%;

}

.v-img{
 max-height:100px;
}

.precio{
    padding-top: 0;
    position: relative;
   top:30%;
   right: 0;
   
}
.cerrar{
   position: absolute;
   right: 5px;
}
.cerrar1{
   position: absolute;
   right: 20px;
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


*{
   font-family: 'rawline', sans-serif !important;  
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

.puntos_img {
  max-width: 23px;
 position: relative;
 left: 39%;

}
}
</style>