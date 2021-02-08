<template>
    <v-container>
        <v-card 
            v-for="productos in productos"
            :key="productos.nombre" 
            class="primary ml-3 mt-5 " 
            width="93%" >

            <v-row >

                <v-col cols="5" class="ml-n2 mr-0 mt-1">

                    <v-img
                        :src="productos.src" 
                    ></v-img>

                </v-col>

                <v-col cols="7" class="pl-0 ml-0 pt-0 " >
                    
                       
                     <v-card-title class="font-weight-semibold white--text pl-0" style="font-size:17px;">
                                {{ productos.nombre }}
                            
                         <v-btn
                                icon
                                small
                                color="white"
                                class="cerrar"
                                @click="eliminarProducto(productos.nombre);total-=productos.precio;puntos-=(productos.puntos *= productos.value);"
                            >
                            
                                <v-icon>mdi-close</v-icon>
                                
                         </v-btn>
                      </v-card-title>
                    
                    <v-card-subtitle class="pb-0 font-weight-medium white--text pl-0" style="font-size:12px;">
                        {{ productos.info }}
                    </v-card-subtitle>

                    <v-card-actions class="pt-0 mt-0 pl-0">

                     <v-col class="d-flex flex-row pb-0 pl-0 pt-1 ">
                                   
                        <v-btn id ="disminuir" v-on:click="productos.value--; productos.precio-=productos.precio_suma;total-=productos.precio_suma; puntos-=productos.puntos; " x-small outlined color="white" style="font-size:25px;" class="pb-2" >-</v-btn>
                             <input type='number' id="cantidad" :value="Math.abs(productos.value)" class="font-weight-semibold white--text ml-4 mt-n1">   
                        <v-btn id="aumentar" v-on:click="productos.value++;  productos.precio+=productos.precio_suma; total+=productos.precio_suma; puntos+=productos.puntos;"  x-small  color="white" style="font-size:25px;color:#f8744e;"  class="pb-1" elevation="0">+</v-btn>
                     </v-col>

                    </v-card-actions>

                    <v-card-text class="font-weight-medium white--text text-right precio mt-1" style="font-size:24px;" >$
                    {{Math.abs(productos.precio)}}
                    </v-card-text>
                </v-col>

            </v-row>
        </v-card>


        <v-chip
        outlined
        class="mt-12 ml-3"
        >
        <v-row>
            <h3 class="ml-3">TOTAL</h3><h3 class="cerrar mr-2">${{Math.abs(total)}}</h3>
         </v-row>
        </v-chip>

        <p class="aclaracion">Total en puntos:  {{puntos}}</p>

        <v-row class=" justify-center align-center text-center mt-15">
        <v-btn class="font-weight-semibold secondary text-capitalize"  rounded  elevation="0"  @click="dialog=true" > 
                  Comprar
        </v-btn>
        </v-row>


        <v-dialog v-model="dialog" width="500"  transition="dialog-bottom-transition"  class="dialogo mx-0"  overflow-hidden full-screen persistent>
                <v-card class=" justify-center align-center text-center">
                    <v-btn
                                icon
                                small
                                color="black"
                                class="cerrar mt-2 mr-2"
                                
                                @click="dialog=false"
                            >
                            
                                <v-icon>mdi-close</v-icon>
                                
                         </v-btn>
                <v-card-title class="px-12 mb-4 mt-3">
                    Elegí dónde queres consumir tu compra
                </v-card-title>
                
                <p class="mb-0">Lo espero en casa</p>

                <v-card-actions class=" justify-center align-center text-center"> 
                    <v-btn color="secondary" class="secondary text-capitalize" to="formulario_delivery"> 
                        <v-img src="/images/iconos/delivery.svg" class="mr-2" max-width="30"></v-img>
                        Delivery
                    </v-btn>
                </v-card-actions>

                  <p class="mt-4 mb-0">Lo paso a buscar</p>

                <v-card-actions class=" justify-center align-center text-center"> 
                    <v-btn color="secondary" class="secondary text-capitalize"  to="sucursales" > 
                         <v-img src="/images/iconos/sucursal_blanco.svg" class="mr-2" max-width="30"></v-img>
                        Retiro en sucursal
                    </v-btn>
                </v-card-actions>

            </v-card>
            </v-dialog>
    </v-container>
</template>

<script>
export default {
    data: () => ({
      inicio: 1,
      dialog: false,
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
        total: 265,
        puntos: 8,
    }

    
    ),
       
     methods: {
        
         eliminarProducto(nombre){
                this.productos= this.productos.filter(e => e.nombre != nombre) ;
                
                if(this.productos==0){
                    window.location.href = 'carrito_vacio';
                }
            },
     }
}
</script>

<style lang="scss" scoped>

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
.cerrar{
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
    height: 50%;
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

}
</style>