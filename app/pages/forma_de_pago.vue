<template>
    <v-container fluid>
        <toolbar />
            <v-row class="justify-center text-center mt-8">
                <h3 class="text-left parrafo mt-5 mb-3"> Elegí la forma de pago </h3>
                    <v-col
                    v-for="(producto, i) in productos"
                    :key="i"
                    cols="12"
                    class="text-center"
                    >
                    
                    <v-card class="mt-2 card_style"> 
                        <div class="d-flex flex-no-wrap ml-7 round" style="height: 50px"> 
                            <v-radio-group v-model="radioGroup" @change="inputChange">
                            <v-radio
                                :label="`${producto.title}`"
                                color="secondary"
                                class="checkbox-round" 
                                :key="producto"
                                :value="producto"
                            ></v-radio>
                            </v-radio-group>

                            <div id="disp" style= 
                                "color:green; font-size:18px; font-weight:bold;"> 
                            </div>
                        </div>
                        
                    </v-card>
                       
                    </v-col>
            </v-row>
    </v-container>
</template>

<script>
export default {
    model: {
        prop: 'values',
        event: 'change'
        },
    data: () => ({
        
      formulario_efectivo: '/formulario_efectivo',
      mercado_pago: '/mercado_pago',
      tarjetas: '/tarjetas',
      radioGroup: 1,
      
      productos: [
          {
          title:'Efectivo',
          to: 1
         },
         {
          title:'Mercado Pago',
          to: 2 
         },

         {
          title:'Tarjeta de débito',
          to: 3
         },

         {
          title:'Tarjeta de crédito',
          to: 3
         },

         {
          title:'Transferencia',
          to: 3
         },
      ],
    }),
    methods: {
            inputChange(e) {
            console.log(e.target.value)
            this.$emit('change', event.target.value)
            }

    }

}
</script>

<style scoped>
 
 * {
     font-family: 'Raleway', sans-serif;
 }

 .card_style {
     border-radius: 23px !important;
     text-align: center;
     justify-content: center;
    
 }
 
 .v-card {
     border: 2px solid #184042 !important ;
 }


 .v-radio {
     margin-top: -0.5em !important;
 }

 .parrafo {
     margin-left: -3em !important;
     color: #184042;

 }

</style>