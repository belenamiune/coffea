<template>
    <v-container fluid>
        <toolbar />
            <v-row class="justify-center text-center mt-8">
                <h3 class="text-left parrafo mt-5 mb-3"> Elegí la forma de pago </h3>
                    <v-col
                    cols="12"
                    class="text-center"
                    >
                    
                    <v-card class="mt-2 card_style"> 
                        <div class="d-flex flex-no-wrap ml-7 round" style="height: 50px"> 
                             
                             <label class="mt-3"><input type="radio" name="category_id" @change="onChange($event)" class="form-control" value="1"> Efectivo</label>
                            
                            <div id="disp" style= 
                                "color:green; font-size:18px; font-weight:bold;"> 
                            </div>
                        </div>
                        
                    </v-card>
                       
                    </v-col>

                    <v-col
                    cols="12"
                    class="text-center"
                    >
                    
                    <v-card class="mt-2 card_style"> 
                        <div class="d-flex flex-no-wrap ml-7 round" style="height: 50px"> 
                             
                             <label class="mt-3"><input type="radio" name="category_id" @change="onChange($event)" class="form-control" value="2"> Mercado pago</label>
                            
                            <div id="disp" style= 
                                "color:green; font-size:18px; font-weight:bold;"> 
                            </div>
                        </div>
                        
                    </v-card>
                       
                    </v-col>

                    <v-col
                    cols="12"
                    class="text-center"
                    >
                    
                    <v-card class="mt-2 card_style"> 
                        <div class="d-flex flex-no-wrap ml-7 round" style="height: 50px"> 
                             
                             <label class="mt-3"><input type="radio" name="category_id" @change="onChange($event)" class="form-control" value="3"> Tarjeta de débito</label>
                            
                            <div id="disp" style= 
                                "color:green; font-size:18px; font-weight:bold;"> 
                            </div>
                        </div>
                        
                    </v-card>
                       
                    </v-col>

                    
                    <v-col
                    cols="12"
                    class="text-center"
                    >
                    
                    <v-card class="mt-2 card_style"> 
                        <div class="d-flex flex-no-wrap ml-7 round" style="height: 50px"> 
                             
                             <label class="mt-3"><input type="radio" name="category_id" @change="onChange($event)" class="form-control" value="3"> Tarjeta de crédito</label>
                            
                            <div id="disp" style= 
                                "color:green; font-size:18px; font-weight:bold;"> 
                            </div>
                        </div>
                        
                    </v-card>
                       
                    </v-col>

                    
                    <v-col
                    cols="12"
                    class="text-center"
                    >
                    
                    <v-card class="mt-2 card_style"> 
                        <div class="d-flex flex-no-wrap ml-7 round" style="height: 50px"> 
                             
                             <label class="mt-3"><input type="radio" name="category_id" @change="onChange($event)" class="form-control" value="3"> Transferencia </label>
                            
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
    data: () => ({
    }),
    methods: {
             onChange(event) {
              var optionText = event.target.value;
              console.log(optionText);

              if(event.target.value == 1) {
                  location.href ="/formulario_efectivo";
              }
              if (optionText == 2) {
                  location.href = "/mercado_pago";
              }
              if (event.target.value == 3) {
                   location.href = "/tarjetas";
              }
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