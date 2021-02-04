<template>
<v-container fluid >
     <toolbar />
    
            <v-col cols="12" :class="`rounded-t-xl` "  class=" text-center text-no-wrap secondary margin " >
            
            </v-col>

        <v-row  class="margin_img justify-center align-center ">
             
            </v-row>
            
            <v-row class="margin_img2 justify-center align-center mt-12 white--text"  ><h1 class="font-weight-semibold">Completa los datos</h1> </v-row>
            
            <v-row>
            <v-form class="margin_img2 justify-center align-center mt-6">
                <v-container>
                    <v-row>
                       
                        <v-col cols="12">
                             <v-label>Nombre Completo</v-label>
                             <v-text-field
                                label="Sofía Benza"
                                placeholder="Nombre"
                                solo  
                             ></v-text-field>
                            </v-col>

                           <v-col cols="12" class="mt-n6">
                                <v-label>DNI</v-label>
                                <v-text-field
                                  label="41876532"
                                  solo 
                                ></v-text-field>
                           </v-col>

                            <v-col cols="12" class="mt-n6">
                                <v-label>Teléfono</v-label>
                                <v-text-field
                                    label="03547875621"
                                    placeholder="Teléfono"
                                    solo  
                                ></v-text-field>
                            </v-col>

                               <v-col cols="6" class="mt-n6">
                                <v-label>Tipo de tarjeta</v-label>
                                    <v-select
                                      v-model="select"
                                      :hint="`${select.state}`"
                                      :items="items"
                                      item-text="state"
                                      label="Visa"
                                      persistent-hint
                                      return-object
                                      single-line
                                      solo
                                    ></v-select>
                            </v-col>

                            <v-col cols="6" class="mt-n6">
                                <v-label style="word-break: break-all">Número</v-label>
                                <v-text-field
                                    label=""
                                    placeholder="15151165116"
                                    solo 
                                    type="num" 
                                ></v-text-field>
                                    
                            </v-col>

                            <v-col cols="5" class="mt-n6">
                                <v-label style="word-break: break-all">Vencimiento</v-label>
                                <v-text-field
                                    label=""
                                    placeholder="02/2030"
                                    solo 
                                    type="num" 
                                ></v-text-field>
                                    
                            </v-col>

                               <v-col cols="7" class="mt-n6">
                                <v-label style="word-break: break-all">Código de seguridad</v-label>
                                <v-text-field
                                    label=""
                                    placeholder="***"
                                    solo 
                                    type="num" 
                                ></v-text-field>
                                    
                            </v-col>


                    </v-row>
                </v-container>
            </v-form>
            </v-row>

            <v-row  class=" justify-center align-center primary button_2" >
                    <v-btn 
                    class="font-weight-semibold primary justify-center align-center pa-4 mt-5 mb-10  margin_img margin custom-transform-class text-none" 
                    elevation="6" 
                    rounded
                    to="confirmar_compra"> 
                         Confirmar compra
                    </v-btn>
                 </v-row>
           
        

</v-container>
</template>

<script>
 export default {
    data () {
        
      
      return {
        overlay: false,
        alert: true,
        show1: false,
        select: { state: ''},
        items: [
                { state: 'Visa'},
                { state: 'Mastercard'},
                { state: 'Cabal'},
                { state: 'Naranja'},
                { state: 'Galicia'},
             ],
       }

    }
 }

  
</script>

<style lang="scss" scoped>
.margin{
    position:absolute;
    top:200px;
    left:0px;
    bottom:0;
    height: 90%;
    padding-bottom: 0;
    z-index:1;
  
}

.margin_img{
    position: relative;;
    top:80px;
    bottom: 0;
    z-index:2;
}

.margin_img2 {
    position: relative;;
    top: 180px;
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

.button_2 {
    margin-top: 5em;
}

label {
    font-size: 14px;
}


</style>