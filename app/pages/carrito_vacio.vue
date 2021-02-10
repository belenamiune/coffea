<template>

    <v-container fluid>
        <toolbar />
                <v-row class="justify-center mt-8" >
                    <v-col class="justify-center">
             
                    <p class="text-center parrafo"> El carrito de compras 
    se encuentra vacío </p>

                    <img src="../static/images/carrito_vacio.png" class="mt-5 mb-3">

                    <v-container>
                                <v-row>
                                    <v-col class="text-center">
                                        <v-btn
                                            class="mr-4 mt-6 text-center custom-transform-class text-none"
                                            @click="submit"
                                            color="secondary"
                                            rounded
                                            to="categorias"
                                        >
                                            
                                            Comprar
                                        </v-btn>

                                        </v-col>
                                </v-row>
                            </v-container>

                    </v-col>
            
         
                </v-row>

        
    </v-container>

 
   
</template>

<script>
export default {
   
}

</script>

<style>

* {
    font-family: 'Raleway',sans-serif;
}

img {
    max-width: 250px;
    margin-left: 1em !important;
}

.parrafo {
    font-size: 20px;
}


@media screen and (min-width: 320px){
    
    .parrafo {
        white-space: break-spaces;
        margin-bottom: 2em;

    }
}


</style>